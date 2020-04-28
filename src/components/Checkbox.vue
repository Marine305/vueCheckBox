<template>
  <div class="checkbox" @click="clickChecked()">
    <input
      class="checkbox__item"
      :class="{ checked: checkVisible || checkClass2, disabled: checkClass1 }"
      type="checkbox"
    />
    <label class="checkbox__label">{{ item.title }}</label>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
    },
  },
  data() {
    return {
      checked: false,
    };
  },
  computed: {
    checkVisible() {
      return this.checked;
    },
    checkClass1() {
      const findClass = this.item.option1 === "disabled";
      return findClass;
    },
    checkClass2() {
      const findClass2 = this.item.option2 === "checked";
      return findClass2;
    },
  },
  methods: {
    clickChecked() {
			if(this.item.option1 !== "disabled") {
				this.checked = !this.checked
			}
    },
  },
};
</script>

<style lang="sass">
input
	cursor: pointer
input[type='checkbox']
	-webkit-appearance: none
	-moz-appearance: none
	-ms-appearance: none
	appearance: none
.checkbox
	display: flex
	align-items: center
	justify-content: center
	padding: 7px 0
	&__item
		border-radius: 2px
		border: 2px solid #595959
		width: 18px
		height: 18px
		display: inline-flex
		position: relative
		z-index: 1
		
		&:active
			&::before
				background: rgba(180, 180, 180, 0.3)
		&:hover, &:focus, &:active
			outline: none
			&::before
				content: ''
				position: absolute
				z-index: -1
				top: 50%
				left: 50%
				transform: translate(-50%, -50%)
				width: 35px
				height: 35px
				background: rgba(180, 180, 180, 0.2)
				border-radius: 100%
				display: flex
		&.disabled
			background: #ffffff
			border: 2px solid #9e9e9e
			pointer-events: none
		&.checked
			background: #295df5
			border: 2px solid #295df5
			&:active
				&::before
					background: rgba(75, 75, 255, 0.3)
			&:hover, &:focus, &:active
				&::before
					content: ''
					position: absolute
					z-index: -1
					top: 50%
					left: 50%
					transform: translate(-50%, -50%)
					width: 35px
					height: 35px
					background: rgba(75, 75, 255, 0.2)
					border-radius: 100%
					display: flex
			&::after
				content: ''
				position: absolute
				top: -1px
				left: -1px
				width: 16px
				height: 16px
				fill: #fff
				color: #fff
				background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' fill='none' stroke='white' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' class='feather feather-check' viewBox='0 0 24 24'%3E%3Cdefs/%3E%3Cpath d='M20 6L9 17l-5-5'/%3E%3C/svg%3E")

			&.disabled
				background: #9e9e9e
				border: 2px solid #9e9e9e
				pointer-events: none

	&__label
		margin-left: 10px
</style>
