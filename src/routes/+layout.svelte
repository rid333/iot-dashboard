<script>
    import "../app.css";
    import Sidebar from "$lib/components/ui/sidebar/sidebar.svelte";
    import Topbar from "$lib/components/ui/topbar/topbar.svelte";
</script>

<body class="flex dark">
    <Sidebar />
    <main>
        <Topbar />
        <slot />
    </main>
</body>
