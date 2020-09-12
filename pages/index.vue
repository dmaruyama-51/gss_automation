<template>
  <div class='container'>
    <h1>SpreadSheet の更新を自動反映</h1>
    <p></p>
    <div>
      <table class='table table-striped'>
        <thead>
          <tr>
            <th scope="col">日付</th>
            <th scope="col">曜日</th>
            <th scope="col">天気</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for='(item, i) in items' :key='i'>
            <td>{{item.日付}}</td>
            <td>{{item.曜日}}</td>
            <td>{{item.天気}}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData(){
    const url = encodeURI('https://api.steinhq.com/v1/storages/5f5646be5d3cdc44fcd7d432/シート1')
    const {data} = await axios.get(url)
    return {
      items: data
    }
  }
}
</script>

