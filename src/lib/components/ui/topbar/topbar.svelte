<script lang="ts">
    import * as Avatar from "$lib/components/ui/avatar";
    import { Separator } from "$lib/components/ui/separator";
    import * as Select from "$lib/components/ui/select/index.js";

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
</script>

<nav class="flex justify-between px-4 py-2">
    <Select.Root portal={null}>
        <Select.Trigger class="w-[180px]">
            <Select.Value placeholder="Select a sensor" />
        </Select.Trigger>
        <Select.Content>
            <Select.Group>
                <Select.Label>Sensor</Select.Label>
                {#each sensorsId as sensor}
                    <Select.Item value={sensor.value} label={sensor.label}
                        >{sensor.label}</Select.Item
                    >
                {/each}
            </Select.Group>
        </Select.Content>
        <Select.Input name="sensor" />
    </Select.Root>

    <Avatar.Root>
        <Avatar.Image
            src="https://avatars.githubusercontent.com/u/113193641?s=400&u=4fe489f1a74e40830e7f8f21e7450252fd469ead&v=4"
            alt="rid333"
        />
        <Avatar.Fallback>RD</Avatar.Fallback>
    </Avatar.Root>
</nav>

<Separator />
