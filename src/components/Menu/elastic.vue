<template>
    <div>
        <Menu v-bind="propsToPass" @open-menu="openMenu" @close-menu="closeMenu">
            <slot></slot>
        </Menu>
    </div>
</template>

<script>
    import Menu from '../Menu';
    export default {
      name: 'elastic',
      components: {
        Menu: Menu
      },
      data() {
        return {
          propsToPass: {
            isOpen: this.$attrs.isOpen,
            right: this.$attrs.right,
            width: this.$attrs.width,
            disableEsc: this.$attrs.disableEsc,
            noOverlay: this.$attrs.noOverlay,
            onStateChange: this.$attrs.onStateChange
          }
        };
      },
      methods : {
          openMenu () {
              this.$emit("open-menu")
          },
          closeMenu () {
              this.$emit("close-menu")
          }
      }
    };
</script>
