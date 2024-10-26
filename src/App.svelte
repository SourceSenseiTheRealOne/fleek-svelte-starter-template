<script>
  import { Router, links, Route } from "svelte-routing";
  import {
    Header,
    HeaderNav,
    HeaderNavItem,
    SideNav,
    SideNavItems,
    SideNavLink,
    SkipToContent,
    Content,
    InlineNotification,
  } from "carbon-components-svelte";

  import Home from "./routes/Home.svelte";
  import About from "./routes/about/About.svelte";

  let isSideNavOpen = false;
</script>

<div use:links>
  <Router url="">
    <!-- <Header
      company="My"
      platformName="App"
      bind:isSideNavOpen
      expandedByDefault={false}
    >
      <div slot="skip-to-content">
        <SkipToContent />
      </div>

      <HeaderNav>
        <HeaderNavItem text="Home" href="/" />
      </HeaderNav>

      <SideNav bind:isOpen={isSideNavOpen}>
        <SideNavItems>
          <SideNavLink
            text="Home"
            href="/"
            on:click={() => (isSideNavOpen = !isSideNavOpen)}
          />
        </SideNavItems>
      </SideNav>
    </Header> -->

    <Content>
      <Route path="/" component={Home} />
      <Route let:location></Route>
    </Content>

    <Content>
      <Route path="/about" component={About} />
      <Route let:location></Route>
    </Content>
  </Router>
</div>
