<script>
    import { Label } from "$lib/components/ui/label";

    import {
        Timeline,
        TimelineItem,
        TimelineSeparator,
        TimelineDot,
        TimelineConnector,
        TimelineContent,
        TimelineOppositeContent
    } from 'svelte-vertical-timeline';

    const Mar15events = [
        { title: 'Doors open', time: '8:15 am' },
        { title: 'Code', time: '09:30 pm' },
        { title: 'Lunch', time: '12:00 pm' },
        { title: 'Code', time: '01:00 pm' },
        { title: 'Judging', time: '04:00 pm' },
        { title: 'Closing ceremony', time: '05:00 pm' },
        { title: 'Doors close', time: '5:30' },
    ];
</script>

<Timeline position="alternate">
    <Label class="subtitle text-4xl m-0 font-bold text-nowrap">Sunday, March 16</Label>
	{#each Mar15events as event}
		<TimelineItem>
			<TimelineOppositeContent slot="opposite-content">
				
                <Label class="label text-xl m-0 font-bold">{event.time}</Label>
			</TimelineOppositeContent>
			<TimelineSeparator>
				<TimelineDot style="background-color:white"/>
				<TimelineConnector />
			</TimelineSeparator>
			<TimelineContent>
				<Label class="subtitle text-xl m-0 font-bold">{event.title}</Label>
			</TimelineContent>
		</TimelineItem>
	{/each}
</Timeline>