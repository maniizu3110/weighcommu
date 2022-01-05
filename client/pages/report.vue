<template>
  <div>
    <Chart />
  </div>
</template>

<script>
export default {
  name: 'report',
  data() {
    return {
      data: [
        { date: '2021-01-01', friends_count: 100, followers_count: 200 },
        { date: '2021-01-02', friends_count: 120, followers_count: 210 },
        { date: '2021-01-03', friends_count: 140, followers_count: 300 },
        { date: '2021-01-04', friends_count: 140, followers_count: 320 },
        { date: '2021-01-05', friends_count: 160, followers_count: 330 },
        { date: '2021-01-06', friends_count: 167, followers_count: 350 },
        { date: '2021-01-07', friends_count: 173, followers_count: 380 },
        { date: '2021-01-08', friends_count: 177, followers_count: 370 },
        { date: '2021-01-09', friends_count: 189, followers_count: 410 },
      ],
    }
  },
}
</script>
