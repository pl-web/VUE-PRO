<template>
  <div class="form-item">
    <label v-if="label">{{ label }}</label>
    <slot></slot>
    <br />
    <span class="__error__message__" v-if="error">{{ error }}</span>
  </div>
</template>

<script>
import V from "async-validator";
export default {
  name: "FormItem",
  inject: ["form"],
  props: {
    label: {
      type: String,
      default: "",
      required: false,
    },
    prop: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      error: "", // 如果为空，代表校验通过
    };
  },
  mounted() {
    this.$on("validate", () => {
      this.validate();
    });
  },
  methods: {
    validate() {
      // according validate result to dispaly error information or not dispaly the information
      // current value
      const currentValue = this.form.model[this.prop];
      // current rules
      const currentRule = this.form.rules[this.prop];
      // start to validate using the async-validator
      const des = {
        [this.prop]: currentRule,
      };
      const v = new V(des);
      // validate 函数参数为校验源
      v.validate(
        {
          [this.prop]: currentValue,
        },
        (err) => {
          if (err) {
            this.error = err[0].message
          } else {
            this.error = ''
          }
        }
      );
    },
  },
};
</script>

<style scoped>
.form-item {
  margin-top: 10px;
  display: flex;
}
label {
  margin-right: 10px;
}
.__error__message__ {
  font-size: 10px;
  line-height: 100%;
  margin-top: 9px;
  margin-left: 5px;
  color: rgb(226, 21, 21);
}
</style>