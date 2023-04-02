<script lang="ts">
  import "../app.scss";
  import {
    Content,
    Header,
    HeaderGlobalAction,
    HeaderSearch,
    HeaderUtilities,
    SideNav,
    SideNavDivider,
    SideNavItems,
    SideNavLink
  } from "carbon-components-svelte";
  import {ChartNetwork, Settings} from "carbon-icons-svelte";
  import {page} from "$app/stores";
  $: activeUrl = $page.url.pathname;
  let isSideNavOpen = true;

</script>

<Header persistentHamburgerMenu={true} expandedByDefault="{true}" isSideNavOpen="{true}" company="SperaSoft"
        platformName="Console">
  <HeaderUtilities>
    <HeaderGlobalAction aria-label="Settings" icon="{Settings}"/>
    <HeaderSearch/>
  </HeaderUtilities>
</Header>


<SideNav fixed="true" isOpen="{isSideNavOpen}" rail="{!isSideNavOpen}">
  <SideNavItems>
    <SideNavLink
      isSelected="{activeUrl === '/test/1'}"
      icon="{ChartNetwork}" text="Test 1" href="/test/1"/>
    <SideNavLink
      isSelected="{activeUrl === '/test/2'}"
      icon="{ChartNetwork}" text="Test 2" href="/test/2"/>
    <SideNavDivider/>
  </SideNavItems>
</SideNav>

<Content>
  <slot/>
</Content>
