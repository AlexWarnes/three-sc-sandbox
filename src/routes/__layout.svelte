<nav>
  <a href="/discover-three">DiscoverThree</a>
  <a href="/expanse">Expanse</a>
</nav>
<slot />
<style>
  :global(p, a, h1, h2, h3, h4){
    font-family: Verdana, Geneva, Tahoma, sans-serif;
  }
  nav {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
    width: 100%;
    padding: 1rem 1.5rem;
    background-color: #fafbfc;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
  }

  a {
    margin: 0 1rem;
  }

</style>