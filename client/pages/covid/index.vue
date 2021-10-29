<template>
  <div class="covid">
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-center">
            <h1 class="hero-title">
              Covid 19 <span>Coronavirus</span>
            </h1>
          </div>
        </div>
        <div class="row pb-5">
          <div class="col-md-4">
            <div class="text-white text-center">
              <h3>
                New Confirmed
              </h3>
              {{ covidNewConfirmed }}
            </div>
          </div>
          <div class="col-md-4">
            <div class="text-white text-center">
              <h3>
                Total Confirmed
              </h3>
              {{ covidTotalConfirmed }}
            </div>
          </div>
          <div class="col-md-4">
            <div class="text-white text-center">
              <h3>
                Total Deaths
              </h3>
              {{ covidTotalDeaths }}
            </div>
          </div>
        </div>
      </div>
    </div>
    <section class="section">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-md-12">
            <div class="text-center mb-3">
              {{ new Date(Date.now()).toLocaleString() }}
            </div>
            <h2 class="section-title text-center mb-3">
              Country State
            </h2>
            <div v-if="message" class="text-center text-danger mb-3">
              Something went wrong!
            </div>
            <div v-if="loading && !message" class="text-center mb-3">
              LOADING...
            </div>
            <div class="covid-table table-responsive">
              <table class="table table-bordered">
                <thead>
                  <tr>
                    <th scope="col">
                      Country Code
                    </th>
                    <th scope="col">
                      Country
                    </th>
                    <th scope="col">
                      New Confirmed
                    </th>
                    <th scope="col">
                      New Deaths
                    </th>
                    <th scope="col">
                      Total Confirmed
                    </th>
                    <th scope="col">
                      Total Deaths
                    </th>
                  </tr>
                </thead>
                <tbody v-for="(country, index) in covidCountries" :key="index">
                  <tr>
                    <td>{{ country.CountryCode }}</td>
                    <td>{{ country.Country }}</td>
                    <td :class="[country.NewConfirmed > 0 ? 'text-green' : '']">
                      <span v-if="country.NewConfirmed > 0"> + </span> {{ country.NewConfirmed }}
                    </td>
                    <td :class="[country.NewDeaths > 0 ? 'text-red' : '']">
                      <span v-if="country.NewDeaths > 0"> + </span> {{ country.NewDeaths }}
                    </td>
                    <td class="text-blue">
                      {{ country.TotalConfirmed }}
                    </td>
                    <td class="text-blue">
                      {{ country.TotalDeaths }}
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      covidNewConfirmed: null,
      covidTotalConfirmed: null,
      covidTotalDeaths: null,
      covidDate: null,
      covidCountries: null,
      message: false,
      loading: false
    }
  },
  async created () {
    try {
      this.loading = true
      const response = await this.$axios.$get('https://api.covid19api.com/summary')
      this.covidNewConfirmed = response.Global.NewConfirmed
      this.covidTotalConfirmed = response.Global.TotalConfirmed
      this.covidTotalDeaths = response.Global.TotalDeaths
      this.covidCountries = response.Countries
      this.covidDate = response.Date
      this.loading = false
    } catch (error) {
      this.message = true
    }
  }
}
</script>

<style>
.covid-table {
    height: 500px;
    overflow: auto;
}

.covid-table thead th {
    position: sticky;
    top: 0;
    z-index: 1;
    background-color: #F2F2F2;
}

.covid .section-title {
    color: #212529;
}

.text-green {
  color: #41B783;
}

.text-red {
  color: #e95050;
}

.text-blue {
  color:#6868dd;
}
</style>
