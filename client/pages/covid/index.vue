<template>
  <div class="covid">
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-center">
            <h1 class="hero-title">
              {{ covidContent.heroTitle }} <span>{{ covidContent.heroTitleAddition }}</span>
            </h1>
          </div>
        </div>
        <div class="row pb-5">
          <div class="col-md-4 mb-3 mb-md-0">
            <div class="text-white text-center">
              <h3>
                {{ covidContent.heroSubtitleOne }}
              </h3>
              {{ covidNewConfirmed }}
            </div>
          </div>
          <div class="col-md-4 mb-3 mb-md-0">
            <div class="text-white text-center">
              <h3>
                {{ covidContent.heroSubtitleTwo }}
              </h3>
              {{ covidTotalConfirmed }}
            </div>
          </div>
          <div class="col-md-4">
            <div class="text-white text-center">
              <h3>
                {{ covidContent.heroSubtitleThree }}
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
      loading: false,
      covidContent: {
        heroTitle: 'Covid 19',
        heroTitleAddition: 'Coronavirus',
        heroSubtitleOne: 'New Confirmed',
        heroSubtitleTwo: 'Total Confirmed',
        heroSubtitleThree: 'Total Deaths'
      }
    }
  },
  head () {
    return {
      title: 'Covid-19 | Online Creative Agency',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'With a strong sense of aesthetic and an eye for pixel perfection, we pair with our clients to create the best versions of their design ideas. We offer elegant solutions and user experiences which enhance the online presence of a wide variety of businesses. Our team is ready for whatever it is your heart desires, willing to go the extra mile to create your perfect project.'
        }
      ]
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
