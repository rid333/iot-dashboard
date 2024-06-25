<script>
    import "../app.css";
    import Sidebar from "$lib/components/ui/sidebar/sidebar.svelte";
    import Topbar from "$lib/components/ui/topbar/topbar.svelte";
</script>

<!-- <Sidebar /> -->
<!-- <div> -->
<!--     <Topbar /> -->
<!--     <slot /> -->
<!-- </div> -->

<body class="dark">
    <div class="flex">
        <div class=" h-screen">
            <Sidebar />
        </div>
        <div class="flex-1">
            <Topbar />
            <div class="p-4">
                <slot />
            </div>
        </div>
    </div>
</body>
