<script>
    import Logo from "./Logo.svelte";
    import Search from "./Search.svelte";
    import Theme from "./Theme.svelte";
</script>

<header class="header">
    <Logo appName="My Notes" />
    <Search />
    <Theme />
</header>

<style>
    .header {
            padding: 0 5vmax 3vmax 5vmax;
        }
</style>
