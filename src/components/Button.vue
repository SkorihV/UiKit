
<script setup>
  const props = defineProps({
    label: {
      type: String,
      default: 'Кнопка'
    },
    color: {
      type: String,
      default: 'primary'
    },
    rounded: {
      type: Boolean,
      default: false
    },
    disabled: {
      type: Boolean,
      default: false
    },
    outlined: {
      type: Boolean,
      default: false
    },
    icon: {
      type: String
    },
    size: {
      type: String,
      default: 'normal',
      validator(value) {
        return value === 'normal' || value === 'large'
      }
    },
  })
  const emit = defineEmits(['click'])

  const clickOnButton = () => {
    emit("click", props.label)
  }

</script>

<template>
  <button
     @click="clickOnButton"
    :class="[
       'btn',
       `btn_${color}`,
       `btn_${size}`,
      {'btn_rounded': rounded},
      {'btn_disabled': disabled},
      {'btn_icon': icon},
      {'btn_outlined': outlined}
    ]"
  >
      <span v-if="icon">
          <font-awesome-icon :icon="['fa-regular', icon]" />
      </span>
      <span v-else>{{label}}</span>
  </button>
</template>


<style lang="scss" scoped>

.btn {
  margin-right: 10px;
  margin-bottom: 10px;
  padding: 0 20px;
  height: 40px;
  color: #fff;
  border-radius: 7px;
  border: none;
  cursor: pointer;
  font-size: 15px;
  transition: .2s;
  display: flex;
  align-items: center;
  justify-content: center;
  &_primary {
    background: var(--primary);
    border: 1px solid var(--primary);
    &:enabled:hover {
      background: var(--primary-hover);
    }
  }
  &_second {
    background: var(--second);
    border: 1px solid var(--second);
    &:enabled:hover {
      background: var(--second-hover);
    }
  }
  &_success {
    background: var(--success);
    border: 1px solid var(--success);
    &:enabled:hover {
      background: var(--success-hover);
    }
  }
  &_info {
    background: var(--info);
    border: 1px solid var(--info);
    &:enabled:hover {
      background: var(--info-hover);
    }
  }
  &_warning {
    background: var(--warning);
    border: 1px solid var(--warning);
    &:enabled:hover {
      background: var(--warning-hover);
    }
  }
  &_danger {
    background: var(--danger);
    border: 1px solid var(--danger);
    &:enabled:hover {
      background: var(--danger-hover);
    }
  }
  &:disabled {
    opacity: .6;
    cursor: default;
  }
  &_rounded {
    border-radius: 50px;
  }
  &_outlined {
    background: transparent;
    color: #000;
    &:hover {
      color: #fff;
    }
  }
  &_icon {
    padding: 0;
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }
  &_large {
    height: 48px;
    padding: 30px;
  }
}

</style>
