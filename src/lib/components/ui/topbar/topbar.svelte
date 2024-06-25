<script lang="ts">
    import { Check, ChevronsUpDown } from "lucide-svelte";
    import * as Command from "$lib/components/ui/command";
    import * as Popover from "$lib/components/ui/popover";
    import { Button } from "$lib/components/ui/button";

    const sensordId = [
        {
            value: "sensor1",
            label: "Sensor 1",
        },
        {
            value: "sensor2",
            label: "Sensor 2",
        },
        {
            value: "sensor3",
            label: "Sensor 3",
        },
    ];

    let open = false;
    let value = "";
</script>

<Popover.Root bind:open>
    <Popover.Trigger>
        <Button variant="outline">
            Select a sensor...
            <ChevronsUpDown class="ml-2 h-4 w-4 shrink-0 opacity-50" />
        </Button>
    </Popover.Trigger>
    <Popover.Content>Place content for the popover here.</Popover.Content>
</Popover.Root>

