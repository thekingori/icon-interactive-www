<template>
  <header class="header">
    <div class="container">
      <g-link :to="{ name: 'home' }" class="home-link">
        <img src="../../static/icon-logo.svg" :alt="settings.site_name" class="logo" />
      </g-link>
      <nav class="nav">
        <g-link class="nav__link" to="/projects">Work</g-link>
        <g-link class="nav__link" to="/capabilities">Capabilities</g-link>
        <g-link class="nav__link" to="/news">News</g-link>
        <g-link class="nav__link" to="/about">About</g-link>
        <g-link class="nav__link" to="/connect">Connect</g-link>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      logo: require("../../static/icon-logo.svg"),
      settings: require("../../data/theme.json")
    };
  }
};
</script>

<style scoped>
.header {
  position: sticky;
  position: -webkit-sticky;
  top: 0;
  padding: 1rem 0 1rem;
  z-index: 10;
  width: 100%;
  margin-bottom: 2rem;
  background-color: var(--color-base-opacity);
}
.nav {
  display: flex;
  justify-content: center;
  transition: all 1s ease-in-out;
}
.intro {
  display: flex;
  width: 40%;
  justify-content: space-evenly;
  transition: all 1s ease-in-out;
  margin-right: 40%;
}
.intro p {
  font-size: 1.2rem;
}
.header > .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 100%;
}
.home-link {
  text-decoration: none;
}
.logo {
  height: 65px;
  fill: white;
  transition: all 1s ease-in-out;
}
.logo:hover {
  opacity: 0.4;
  filter: blur(3px);
}
.nav > * {
  font-size: 1.2rem;
  font-weight: 600;
  text-decoration: none;
  margin-top: 4px;
  margin-right: 3.5rem;
  padding-bottom: 4px;
  border-bottom: 1px solid;
  border-color: transparent;
  transition: border 0.15s;
}
.nav > *:last-of-type {
  margin-right: 0;
}
.nav > *:hover {
  color: var(--color-highlight);
  transition: all 300ms ease-in;
}
.nav > .active {
  color: var(--color-highlight);
}
@media (max-width: 800px) {
  .header {
    position: relative;
    margin-bottom: 0;
  }
  .nav > * {
    font-size: 1rem;
  }
  .nav {
    flex-direction: column;
    justify-items: right;
  }
  .intro {
    width: 60%;
    margin-right: 5%;
  }
  .nav__link {
    margin: 0;
    text-align: right;
  }
  .nav__link:hover {
    text-decoration: none;
  }
  .intro p {
    font-size: 1rem;
  }
}
</style>
