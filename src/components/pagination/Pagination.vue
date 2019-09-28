<template>
  <div class="pagination">
    <div class="pagination-selected">
      <span>{{ presentPage }}</span> of
      <span>{{ totalPage }}</span>
    </div>
    <div class="pagination-navigation">
      <div class="pagination-left" @click="handlePageChange" name="paginationLeft">
        <svg
          version="1.1"
          id="Capa_1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          width="20px"
          height="20px"
          viewBox="0 0 103.537 103.537"
          style="enable-background:new 0 0 103.537 103.537;"
          xml:space="preserve"
          v-bind:class="{ notActive: !isPaginationLeftActive }"
        >
          <g>
            <g>
              <path
                d="M103.048,12.002c-1.445-3.771-5.679-5.649-9.438-4.207L4.692,41.9c-2.753,1.055-4.603,3.662-4.688,6.609 c-0.087,2.948,1.608,5.656,4.295,6.872l88.917,40.196c0.978,0.44,2,0.65,3.006,0.65c2.784,0,5.442-1.6,6.665-4.302 c1.661-3.678,0.029-8.007-3.648-9.671L26.273,49.277l72.568-27.834C102.61,19.998,104.496,15.771,103.048,12.002z"
              />
            </g>
          </g>
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
        </svg>
      </div>
      <div class="pagination-right"  @click="handlePageChange" name="paginationRight">
        <svg
          version="1.1"
          id="Capa_1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          width="20px"
          height="20px"
          viewBox="0 0 103.536 103.536"
          style="enable-background:new 0 0 103.536 103.536;"
          xml:space="preserve"
             v-bind:class="{ notActive: !isPaginationRightActive }"
        >
          <g>
            <g>
              <path
                d="M0.65,91.928c1.221,2.701,3.881,4.3,6.665,4.3c1.006,0,2.029-0.209,3.006-0.65l88.917-40.195 c2.688-1.216,4.381-3.925,4.295-6.873c-0.085-2.948-1.934-5.554-4.687-6.609L9.929,7.794C6.17,6.352,1.933,8.23,0.489,12.001 c-1.447,3.769,0.438,7.995,4.207,9.44l72.569,27.834L4.299,82.255C0.62,83.92-1.012,88.249,0.65,91.928z"
              />
            </g>
          </g>
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
          <g />
        </svg>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Pagination',
  data() {
    return {
      presentPage: 1,
      startPage: 1,
      totalPage: 50,
      paginationLeftClick: false,
      isPaginationLeftActive: true,
      isPaginationRightActive: true,
    };
  },
  created() {
    this.setPaginationActive();
  },
  methods: {
    handlePageChange(e) {
      if (e.currentTarget.getAttribute('name') === 'paginationLeft' && this.presentPage > this.startPage) {
        this.presentPage = this.presentPage - 1;
        this.setPaginationActive();
      }

      if (e.currentTarget.getAttribute('name') === 'paginationRight' && this.presentPage < this.totalPage) {
        this.presentPage = this.presentPage + 1;
        this.setPaginationActive();
      }
    },
    setPaginationActive() {
      switch (this.presentPage) {
        case this.startPage:
          this.isPaginationLeftActive = false;
          break;
        case this.totalPage:
          this.isPaginationRightActive = false;
          break;
        default:
          this.isPaginationLeftActive = true;
          this.isPaginationRightActive = true;
      }
    },
  },
};
</script>
<style scoped>
.pagination {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 3rem;
}

.pagination-selected {
  font-size: 1.5rem;
  color: #d7d9dd;
}

.pagination-navigation {
  display: flex;
  margin-left: 1.3rem;
}

.pagination-navigation div {
  width: 3rem;
  height: 3rem;
  border: 1px solid #dddddd;
  display: flex;
  justify-content: center;
  align-items: center;
}

.pagination-left {
  border-top-left-radius: 0.5rem;
  border-bottom-left-radius: 0.5rem;
}

.pagination-right {
  border-top-right-radius: 0.5rem;
  border-bottom-right-radius: 0.5rem;
}

.notActive {
  fill: #A8A8A8;
}
</style>
