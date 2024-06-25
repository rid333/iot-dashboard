<script lang="ts">
    import { Check, ChevronsUpDown } from "lucide-svelte";
    import * as Command from "$lib/components/ui/command";
    import * as Popover from "$lib/components/ui/popover";
    import { Button } from "$lib/components/ui/button";
    import * as Avatar from "$lib/components/ui/avatar";
    import { cn } from "$lib/utils.js";
    import { tick } from "svelte";
    import { Separator } from "$lib/components/ui/separator";
    import CommandSeparator from "../command/command-separator.svelte";

    const sensorsId = [
        {
            value: "sensor 1",
            label: "Sensor 1",
        },
        {
            value: "sensor 2",
            label: "Sensor 2",
        },
        {
            value: "sensor 3",
            label: "Sensor 3",
        },
    ];

    $: selectedValue =
        sensorsId.find((f) => f.value === value)?.label ?? "Select a sensor...";

    function closeAndFocusTrigger(triggerId: string) {
        open = false;
        tick().then(() => {
            document.getElementById(triggerId)?.focus();
        });
    }

    let open = false;
    let value = "";
</script>

<nav class="flex justify-between px-4 py-2">
    <Popover.Root bind:open let:ids>
        <Popover.Trigger>
            <Button variant="outline" class="w-[200px] flex justify-between">
                {selectedValue}
                <ChevronsUpDown class="ml-2 h-4 w-4 shrink-0 opacity-50" />
            </Button>
        </Popover.Trigger>
        <Popover.Content class="w-[200px] p-0">
            <Command.Root>
                <Command.Input placeholder="Search sensor ID..." />
                <Command.Empty>No sensor found.</Command.Empty>
                <Command.Group>
                    {#each sensorsId as sensor}
                        <Command.Item
                            value={sensor.value}
                            onSelect={(currentValue) => {
                                value = currentValue;
                                closeAndFocusTrigger(ids.trigger);
                            }}
                        >
                            <Check
                                class={cn(
                                    "mr-2 h-4 w-4",
                                    value !== sensor.value &&
                                        "text-transparent",
                                )}
                            />
                            {sensor.label}
                        </Command.Item>
                    {/each}
                </Command.Group>
            </Command.Root>
        </Popover.Content>
    </Popover.Root>

    <Avatar.Root>
        <Avatar.Image
            src="https://avatars.githubusercontent.com/u/113193641?s=400&u=4fe489f1a74e40830e7f8f21e7450252fd469ead&v=4"
            alt="rid333"
        />
        <Avatar.Fallback>RD</Avatar.Fallback>
    </Avatar.Root>
</nav>

<Separator />
