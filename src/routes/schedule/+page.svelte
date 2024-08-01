<script>
    import { Heading, Table, TableBody, TableBodyCell, TableBodyRow, TableHead, TableHeadCell } from 'flowbite-svelte';
  
    const schedule = [
      {
        day: 'Day 1',
        date: 'Monday, August 19, 2024',
        events: [
          { time: '13:00 - 14:00', description: 'Registration' },
          { time: '14:00 - 17:00', description: 'Opening Talks' },
          { time: '17:00 - 17:30', description: 'Team Building & Brainstorming' },
          { time: '17:30 - 19:00', description: 'Welcome Dinner' },
          { time: '19:00 - 21:00', description: 'Gijang Tour & Networking' },
        ]
      },
      {
        day: 'Day 2',
        date: 'Tuesday, August 20, 2024',
        events: [
          { time: '09:00 - 12:30', description: 'Hacking' },
          { time: '12:30 - 14:00', description: 'Lunch Break' },
          { time: '14:00 - 16:00', description: 'Hacking' },
          { time: '16:00 - 16:30', description: 'Coffee Break' },
          { time: '16:30 - 18:30', description: 'Hacking' },
          { time: '18:30 - 20:00', description: 'Dinner and Networking' },
          { time: '20:00 - 23:00', description: 'Hacking' },
        ]
      },
      {
        day: 'Day 3',
        date: 'Wednesday, August 21, 2024',
        events: [
          { time: '09:00 - 12:00', description: 'Hacking' },
          { time: '12:00 - 13:30', description: 'Lunch Break' },
          { time: '13:30 - 15:00', description: 'Hacking' },
          { time: '15:00 - 15:30', description: 'Coffee Break' },
          { time: '15:30 - 18:30', description: 'Hacking' },
          { time: '18:30 - 20:00', description: 'Dinner and Networking' },
          { time: '20:00 - 23:00', description: 'Hacking' },
        ]
      },
      {
        day: 'Day 4',
        date: 'Thursday, August 22, 2024',
        events: [
          { time: '09:00 - 11:30', description: 'Final Presentations' },
          { time: '11:30 - 12:00', description: 'Closing Remarks' },
        ]
      }
    ];
  </script>
  
  <div class="container mx-auto py-8 px-10 md:px-36 bg-white shadow-lg">
    <Heading tag="h1" class="text-3xl md:text-5xl font-bold mb-8 text-center">Hackathon Schedule</Heading>
    
    <div class="md:text-2xl text-center mb-8">
      <p>August 19, 2024 - August 22, 2024</p>
      <p>Oceans and Fisheries HRD Institute, Gijang, Busan</p>
    </div>
  
    {#each schedule as day}
      <div class="mb-16">
        <Heading tag="h2" class="text-2xl md:text-4xl font-semibold mb-2">{day.day}</Heading>
        <Heading tag="h3" class="text-xl md:text-2xl text-gray-600 mb-4">{day.date}</Heading>
        
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
  
  <style>
    :global(body) {
      font-size: 18px;
    }
    
    :global(th), :global(td) {
      padding: 1rem !important;
    }
  </style>