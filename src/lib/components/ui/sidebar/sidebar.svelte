<script lang="ts">
    import { House } from "lucide-svelte";
    import { Menu } from "lucide-svelte";
    import { Button } from "$lib/components/ui/button";
</script>

<aside class="flex flex-col gap-y-5 p-5 h-screen bg-red-900">
    <a href="/">
        <Menu class="ml-4" />
    </a>

    <Button variant="default" class="pr-20">
        <House class="mr-2" />
        Button
    </Button>

    <Button variant="ghost" class="pr-20">
        <House class="mr-2" />
        Button
    </Button>

    <Button variant="ghost" class="pr-20">
        <House class="mr-2" />
        Button
    </Button>
</aside>
