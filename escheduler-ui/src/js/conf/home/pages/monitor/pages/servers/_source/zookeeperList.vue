<template>
  <div class="list-model zookeeper-list">
    <div class="table-box">
      <table>
        <tr>
          <th>
            <span>{{$t('#')}}</span>
          </th>
          <th>
            <span>{{$t('host')}}</span>
          </th>
          <th>
            <span>{{$t('Number of connections')}}</span>
          </th>
          <th>
            <span>watches {{$t('Number')}}</span>
          </th>
          <th>
            <span>{{$t('Sent')}}</span>
          </th>
          <th>
            <span>{{$t('Received')}}</span>
          </th>
          <th>
            <span>leader/follower</span>
          </th>
          <th>
            <span>{{$t('Min latency')}}</span>
          </th>
          <th>
            <span>{{$t('Avg latency')}}</span>
          </th>
          <th>
            <span>{{$t('Max latency')}}</span>
          </th>
          <th>
            <span>{{$t('Node count')}}</span>
          </th>
          <th>
            <span>{{$t('Query time')}}</span>
          </th>
          <th style="text-align: center">
            <span>{{$t('Node self-test status')}}</span>
          </th>
        </tr>
        <tr v-for="(item, $index) in list" :key="$index">
          <td>
            <span>{{$index + 1}}</span>
          </td>
          <td>
            <span>
              <a href="javascript:" class="links">{{item.hostname}}</a>
            </span>
          </td>
          <td><span>{{item.connections}}</span></td>
          <td>
            <span>{{item.watches}}</span>
          </td>
          <td>
            <span>{{item.sent}}</span>
          </td>
          <td>
            <span>{{item.received}}</span>
          </td>
          <td><span>{{item.mode}}</span></td>
          <td>
            <span>{{item.minLatency}}</span>
          </td>
          <td>
            <span>{{item.avgLatency}}</span>
          </td>
          <td>
            <span>{{item.maxLatency}}</span>
          </td>
          <td>
            <span>{{item.nodeCount}}</span>
          </td>
          <td>
            <span>{{item.date | formatDate}}</span>
          </td>
          <td>
            <span class="state">
              <i class="iconfont success" v-if="item.state">&#xe607;</i>
              <i class="iconfont error" v-else>&#xe626;</i>
            </span>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'zookeeper-list',
    data () {
      return {
        list: []
      }
    },
    props: {
      list: Array
    }
  }
</script>

<style lang="scss" rel="stylesheet/scss">
  .zookeeper-list {
    .state {
      text-align: center;
      display: block;
      >i {
        font-size: 18px;
      }
      .success {
        color: #33cc00;
      }
      .error {
        color: #ff0000;
      }
    }
  }
</style>

