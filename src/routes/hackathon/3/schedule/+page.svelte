<script>
    import { Heading, Table, TableBody, TableBodyCell, TableBodyRow, TableHead, TableHeadCell } from 'flowbite-svelte';

    const schedule = [
      {
        day: 'Day 1',
        date: 'Monday, February 9, 2026',
        events: [
          { time: '13:00 - 14:00', description: 'Registration' },
          { time: '14:00 - 14:15', description: 'Welcome reception: Heetak Lee and Jeongbin Park' },
          { time: '14:15 - 15:15', description: 'Data Talk' },
          { time: '15:15 - 17:30', description: 'Opening Talks' },
          { time: '17:30 - 19:00', description: 'Welcome Dinner (SCSOK covers only this specific dinner)' },
          { time: '19:00 - 21:00', description: 'Networking & Hacking' },
        ]
      },
      {
        day: 'Day 2',
        date: 'Tuesday, February 10, 2026',
        events: [
          { time: '09:00 - 12:00', description: 'Hacking' },
          { time: '12:00 - 13:30', description: 'Lunch' },
          { time: '13:30 - 18:00', description: 'Hacking' },
          { time: '18:00 - 20:00', description: 'Dinner' },
          { time: '20:00 - 23:00', description: 'Networking & Hacking' },
        ]
      },
      {
        day: 'Day 3',
        date: 'Wednesday, February 11, 2026',
        events: [
          { time: '09:00 - 12:00', description: 'Hacking' },
          { time: '12:00 - 13:30', description: 'Lunch' },
          { time: '13:30 - 18:00', description: 'Hacking' },
          { time: '18:00 - 20:00', description: 'Dinner' },
          { time: '20:00 - 23:00', description: 'Networking & Hacking' },
        ]
      },
      {
        day: 'Day 4',
        date: 'Thursday, February 12, 2026',
        events: [
          { time: '09:00 - 12:00', description: 'Hacking' },
          { time: '12:00 - 13:30', description: 'Lunch' },
          { time: '13:30 - 18:00', description: 'Hacking' },
          { time: '18:00 - 20:00', description: 'Dinner' },
          { time: '20:00 - 23:00', description: 'Networking & Hacking' },
        ]
      },
      {
        day: 'Day 5',
        date: 'Friday, February 13, 2026',
        events: [
          { time: '09:00 - 11:30', description: 'Final Presentations' },
          { time: '11:30 - 12:00', description: 'Closing Remarks' },
        ]
      }
    ];
</script>

<div class="container mx-auto py-8 px-10 md:px-36 bg-white shadow-lg">
    <Heading tag="h2" class="text-3xl font-bold mb-8">Schedule</Heading>

    <p class="text-gray-600 mb-8">
        *For meals, you may utilize the on-site IBS cafeteria (Lunch: 5,000 KRW, Dinner: 4,500 KRW) or explore the dining options at the nearby Shinsegae Department Store.
    </p>

    {#each schedule as day}
      <div class="mb-16">
        <Heading tag="h3" class="text-2xl md:text-3xl font-semibold mb-2">{day.day}</Heading>
        <p class="text-xl text-gray-600 mb-4">{day.date}</p>

        <Table striped={true} class="text-lg">
          <TableHead>
            <TableHeadCell class="text-lg md:text-xl">Time</TableHeadCell>
            <TableHeadCell class="text-lg md:text-xl">Event</TableHeadCell>
          </TableHead>
          <TableBody>
            {#each day.events as event}
              <TableBodyRow>
                <TableBodyCell style="width: 200px">{event.time}</TableBodyCell>
                <TableBodyCell>{event.description}</TableBodyCell>
              </TableBodyRow>
            {/each}
          </TableBody>
        </Table>
      </div>
    {/each}
</div>
