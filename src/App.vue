<template>
  <div>
    <notifications></notifications>
    <router-view :key="$route.fullPath"></router-view>
    <authenticator>
      <main>
        <div>
          <nav class="nav">
            <ul class="list">
              <li><router-link class="routerLink" to="/chat">Chat</router-link></li>
              <li><router-link class="routerLink" to="/ai">AI</router-link></li>
              <li><router-link class="routerLink" to="/geo">Geo</router-link></li>
            </ul>
          </nav>
        </div>
        <section>
          <router-view/>
        </section>
      </main>
    </authenticator>
  </div>
  
</template>

<script>
  export default {
    methods: {
      disableRTL() {
        if (!this.$rtl.isRTL) {
          this.$rtl.disableRTL();
        }
      },
      toggleNavOpen() {
        let root = document.getElementsByTagName('html')[0];
        root.classList.toggle('nav-open');
      }
    },
    mounted() {
      this.$watch('$route', this.disableRTL, { immediate: true });
      this.$watch('$sidebar.showSidebar', this.toggleNavOpen)
    }
  };
</script>

<style lang="scss"></style>
