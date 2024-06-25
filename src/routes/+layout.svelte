<script>
    import "../app.css";
    import Sidebar from "$lib/components/ui/sidebar/sidebar.svelte";
    import Topbar from "$lib/components/ui/topbar/topbar.svelte";
</script>

<body class="dark bg-neutral-950">
    <div class="flex">
        <div class=" h-screen">
            <Sidebar />
        </div>
        <div class="flex-1">
            <Topbar />
            <slot />
        </div>
    </div>
</body>
