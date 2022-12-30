<script>
  import { Button, Icon, ButtonGroup, El } from "@ubeac/svelte";
  import "../../../svelte/static/css/tabler.css";

  let icon = "copy";

  async function copy() {
    await navigator.clipboard.writeText("npm install @ubeac/svelte");
    icon = "check";

    setTimeout(() => {
      icon = "copy";
    }, 3000);
  }
</script>

<El
  textAlign="center"
  bgColor="secondary"
  bgGradient
  bgOpacity="10"
  display="flex"
  class="el-1 flex-column"
  alignItems="center"
  justifyContent="center"
  p="3"
  gap="4"
  h="100"
>
  <El my="5" display="flex" alignItems="center" justifyContent="center">
    <El
      col="4"
      class="img img-ubeac"
      tag="img"
      borderRadius="circle"
      src="/ubeac_400x400.png"
    />
    <El class="large-text" col="2=4">+</El>
    <El
      col="4"
      class="img img-svelte"
      tag="img"
      borderRadius="circle"
      src="/svelte_1000x1000.png"
    />
  </El>

  <El fontSize="4">
    <El class="large-text">uBeac's Svelte components</El>
    <El mt="2" class="medium-text" textMuted>
      Opinionated Svelte component UI library by uBeac
    </El>
  </El>

  <El class="btn-list main-buttons" size="lg" gap="3">
    <Button
      px="4"
      href="https://svelte.ubeac.io/docs"
      size="lg"
      color="primary"
    >
      Get Started
    </Button>

    <Button
      px="4"
      href="https://github.com/ubeac/svelte"
      size="lg"
      color="github"
    >
      <Icon size="xl" name="brand-github" />
      Source Code
    </Button>
  </El>
</El>

<El
  textAlign="center"
  bgColor="secondary"
  bgGradient
  bgOpacity="25"
  display="flex"
  class="el-2 flex-column"
  alignItems="center"
  justifyContent="center"
  p="5"
  gap="3"
  h="75"
>
  <El class="medium-text">
    To install uBeac Components in your existing Svelte project:
  </El>
  <El
    class="text-terminal"
    border
    display="flex"
    gap="3"
    shadow="lg"
    textColor="light"
    p="3"
    borderRoundSize="3"
    bgColor="github"
  >
    <El>npm install @ubeac/svelte</El>
    <El display="flex" on:click={copy}>
      <Icon name={icon} />
    </El>
  </El>
</El>

<El bgOpacity="75" textColor="light" p="3" textAlign="center" bgColor="github">
  &copy; {new Date().getFullYear()} ubeac.io
</El>

<style>
  :global(.large-text) {
    letter-spacing: -2px;
    line-height: 34px;
    font-size: 42px;
    font-weight: 200;
  }

  :global(.medium-text) {
    line-height: 24px;
    font-size: 22px;
    font-weight: 300;
  }

  :global(.text-terminal) {
    font-family: monospace;
    text-shadow: 0 0 1px blue;
    font-size: 18px;
  }

  :global(.img) {
    width: 180px;
  }

  :global(.img-ubeac) {
    box-shadow: 0 0 5rem 5rem #376ccf40;
  }
  :global(.img-svelte) {
    box-shadow: 0 0 5rem 5rem #fe3c0040;
  }

  @media (max-width: 500px) {
    :global(.img) {
      width: 130px;
    }

    :global(.main-buttons) {
      flex-direction: column;
    }
  }
</style>
