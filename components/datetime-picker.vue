<script>
export default {
  name: 'DatetimePicker'
}
</script>

<template>
  <vue-date-picker class="datatime-picker" v-bind="$attrs" v-on="$listeners" />
</template>

<style lang="scss">
$primaryColor: #005caf;
@mixin flexCenter {
  display: flex;
  justify-content: center;
  align-items: center;
}

.mx-time {
  &-header {
    height: 40px;
    line-height: 40px;

    &-title {
      font-size: 16px;
    }
  }

  &-content {
    height: 250px;
  }
}

.mx-calendar {
  width: 290px;

  &-content {
    height: 244px;
  }

  &-header {
    &-label .mx-btn {
      font-size: 16px;
    }

    .mx-btn-icon-left,
    .mx-btn-icon-right {
      @include flexCenter;
      width: 32px;
      height: 32px;
      border-radius: 50%;
    }

    .mx-btn-icon-double-left,
    .mx-btn-icon-double-right {
      display: none;
    }
  }
}

.mx-table {
  @include flexCenter;
  flex-flow: column nowrap;

  tbody {
    margin-bottom: auto;
  }

  tr {
    display: flex;
    margin: 1px 0;
  }

  th {
    @include flexCenter;
    width: 32px;
    margin: 0 2px;
  }
}

.mx-date-row .cell {
  @include flexCenter;
  border-radius: 50%;
  width: 32px;
  margin: 0 2px;
}
</style>
