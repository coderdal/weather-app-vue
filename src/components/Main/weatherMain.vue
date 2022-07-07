<template>
  <div v-if="isLoading" class="loading">
    <h1>Loading...</h1>
  </div>
  <section v-else>
    <div class="mainData">
      <h1>
        <span>{{ data.city }}</span
        >, {{ data.country }}
      </h1>
      <p>{{ getCurrentDate() }}</p>

      <img
        :src="'../../assets/weatherIcons/' + data.icon + '.png'"
        alt="weather icon"
      />

      <h2>{{ data.temp }}°</h2>

      <h3>{{ data.description }}</h3>
    </div>
    <div class="sideData">
      <h2>Statistics</h2>

      <div class="data">
        <h2>Humidity</h2>
        <div>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="#22C55E"
          >
            <path
              d="M9.019 15.404c-.194 0-.335-.121-.422-.364-.087-.242-.131-.61-.131-1.102s.044-.858.131-1.097c.087-.238.228-.358.422-.358.372 0 .558.485.558 1.454 0 .979-.186 1.467-.558 1.467zm5.957.477c-.194 0-.335.119-.422.358-.087.239-.131.604-.131 1.097s.044.86.131 1.102c.087.242.228.364.422.364.372 0 .558-.489.558-1.466 0-.97-.186-1.455-.558-1.455zm5.024.194c0 4.378-3.579 7.925-8 7.925-4.421 0-8-3.547-8-7.925 0-5.887 5.667-7.117 8-16.075 2.333 8.958 8 10.188 8 16.075zm-10.993.533c.667 0 1.173-.224 1.518-.672.345-.448.518-1.118.518-2.01 0-.853-.175-1.51-.526-1.969-.351-.46-.854-.689-1.51-.689-1.338 0-2.007.886-2.007 2.659 0 .869.174 1.533.524 1.992.349.46.843.689 1.483.689zm6.038-5.218h-1.396l-4.718 8.505h1.396l4.718-8.505zm1.955 5.934c0-.853-.176-1.51-.527-1.969-.351-.46-.854-.689-1.51-.689-1.338 0-2.007.886-2.007 2.658 0 .865.174 1.527.523 1.987.35.459.845.689 1.485.689.667 0 1.173-.224 1.518-.672.345-.448.518-1.116.518-2.004z"
            />
          </svg>
          {{ data.humidity }}<span>%</span>
        </div>
      </div>

      <div class="data">
        <h2>Wind Status</h2>
        <div>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
          >
            <path
              d="M11 10h-11v-2h11c.552 0 1-.448 1-1s-.448-1-1-1c-.403 0-.747.242-.905.587l-1.749-.956c.499-.965 1.494-1.631 2.654-1.631 3.971 0 3.969 6 0 6zm7 7c0-1.656-1.344-3-3-3h-15v2h15c.552 0 1 .448 1 1s-.448 1-1 1c-.403 0-.747-.242-.905-.587l-1.749.956c.499.965 1.494 1.631 2.654 1.631 1.656 0 3-1.344 3-3zm1.014-7.655c.082-.753.712-1.345 1.486-1.345.827 0 1.5.673 1.5 1.5s-.673 1.5-1.5 1.5h-20.5v2h20.5c1.932 0 3.5-1.568 3.5-3.5s-1.568-3.5-3.5-3.5c-1.624 0-2.977 1.116-3.372 2.617l1.886.728z"
            />
          </svg>
          {{ data.wind }}<span>km/s</span>
        </div>
      </div>

      <div class="data">
        <h2>Pressure</h2>
        <div>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="#B91C1C"
            style="width: 34px; height: 34px"
          >
            <path
              d="M7.69,13.2c0-0.99,0.19-1.94,0.58-2.85c0.39-0.91,0.91-1.68,1.57-2.33s1.44-1.17,2.34-1.56c0.9-0.39,1.85-0.58,2.84-0.58
	c0.99,0,1.94,0.19,2.85,0.58c0.9,0.39,1.68,0.91,2.33,1.56c0.65,0.65,1.17,1.43,1.56,2.33s0.58,1.85,0.58,2.85
	c0,1.62-0.48,3.06-1.44,4.34c-0.96,1.27-2.2,2.14-3.71,2.61v3.29h-4.24v-3.25c-1.54-0.45-2.81-1.32-3.79-2.61S7.69,14.83,7.69,13.2zM9.3,13.2c0,1.55,0.56,2.88,1.69,3.99c1.11,1.12,2.45,1.68,4.02,1.68c1.03,0,1.99-0.25,2.86-0.76c0.88-0.51,1.57-1.2,2.09-2.07
	c0.51-0.87,0.77-1.82,0.77-2.85c0-0.77-0.15-1.5-0.45-2.21s-0.71-1.31-1.22-1.82c-0.51-0.51-1.12-0.92-1.83-1.22
	c-0.71-0.3-1.44-0.45-2.21-0.45c-0.77,0-1.5,0.15-2.21,0.45s-1.31,0.71-1.82,1.22c-0.51,0.51-0.92,1.12-1.22,1.82
	C9.45,11.7,9.3,12.43,9.3,13.2z M9.88,13.56v-0.72h2.17v0.72H9.88z M10.97,10.02l0.52-0.52l1.52,1.52l-0.52,0.53L10.97,10.02zM13.5,14.95c0-0.42,0.15-0.78,0.44-1.09c0.29-0.31,0.65-0.47,1.06-0.48l2.73-4.49l0.66,0.35l-2.02,4.83
	c0.18,0.25,0.26,0.54,0.26,0.88c0,0.44-0.15,0.81-0.46,1.11c-0.31,0.3-0.68,0.45-1.12,0.45c-0.43,0-0.8-0.15-1.1-0.45
	C13.65,15.76,13.5,15.39,13.5,14.95z M14.81,10.28V8.12h0.69v2.17H14.81z M17.75,13.55v-0.74h2.17v0.74H17.75z"
            />
          </svg>
          {{ data.pressure }}<span>hPa</span>
        </div>
      </div>

      <div class="data">
        <h2>Visibility</h2>
        <div>
          <svg
            clip-rule="evenodd"
            fill-rule="evenodd"
            stroke-linejoin="round"
            stroke-miterlimit="2"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
            fill="#7E22CE"
            style="width: 34px; height: 34px"
          >
            <path
              d="m11.998 5c-4.078 0-7.742 3.093-9.853 6.483-.096.159-.145.338-.145.517s.048.358.144.517c2.112 3.39 5.776 6.483 9.854 6.483 4.143 0 7.796-3.09 9.864-6.493.092-.156.138-.332.138-.507s-.046-.351-.138-.507c-2.068-3.403-5.721-6.493-9.864-6.493zm.002 3c2.208 0 4 1.792 4 4s-1.792 4-4 4-4-1.792-4-4 1.792-4 4-4zm0 1.5c1.38 0 2.5 1.12 2.5 2.5s-1.12 2.5-2.5 2.5-2.5-1.12-2.5-2.5 1.12-2.5 2.5-2.5z"
              fill-rule="nonzero"
            />
          </svg>
          {{ data.visibility }}<span>m</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { eventBus } from "../../main";

export default {
  name: "WeatherMain",
  data() {
    return {
      isLoading: true,
      data: {
        city: "izmir",
        country: "tr",
        icon: "01d",
        description: "",
        temp: "",
        humidity: 0,
        wind: 0,
        pressure: 0,
        visibility: 0,
      },
    };
  },
  methods: {
    async fetchData(city) {
      fetch(
        `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=165646a7eea43e8eae8c831b8da3d125&units=metric&lang=en`
      )
        .then((response) => {
          if (response.ok) {
            return response.json();
          }
          console.log("City not found.");
        })
        .then((data) => {
          if (data) {
            this.data.city = data.name;
            this.data.country = data.sys.country;
            this.data.icon = data.weather[0].icon;
            this.data.description = data.weather[0].main;
            this.data.humidity = data.main.humidity;
            this.data.wind = data.wind.speed;
            this.data.pressure = data.main.pressure;
            this.data.visibility = data.visibility;
            this.data.temp = Math.ceil(data.main.temp);
            this.isLoading = false;
          }
        })
        .catch((error) => {
          console.log(error);
        });
    },

    getCurrentDate() {
      let d = new Date();
      let months = [
        "January",
        "February",
        "March",
        "April",
        "May",
        "June",
        "July",
        "August",
        "September",
        "October",
        "November",
        "December",
      ];
      let days = [
        "Sunday",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
      ];
      let day = days[d.getDay()];
      let date = d.getDate();
      let month = months[d.getMonth()];
      let year = d.getFullYear();
      return `${day} ${date} ${month} ${year}`;
    },
  },
  created() {
    this.fetchData("Ankara");
    eventBus.$on("input", (inputData) => {
      this.isLoading = true;
      this.fetchData(inputData);
    });
  },
};
</script>

<style scoped>
section {
  width: 100%;
  display: flex;
  gap: 10px;
  padding: 40px 80px;
}

/* Main Data */

.mainData {
  background: #fff;
  box-shadow: 2px 2px 25px rgba(0, 0, 0, 0.144);
  border-radius: 5px;
  min-width: 50%;
  padding: 20px 15px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.mainData h1 {
  font-size: 2.3em;
  text-align: center;
}

.mainData h1 span {
  text-transform: capitalize;
}

.mainData h2 {
  margin: 4px auto;
}

.mainData p {
  opacity: 0.9;
  font-style: italic;
  font-size: 1.06em;
  margin-top: 4px;
}

.mainData img {
  width: 100px;
  margin: 20px auto;
  -webkit-filter: drop-shadow(5px 5px 5px rgba(34, 34, 34, 0.541));
  filter: drop-shadow(5px 5px 5px rgba(34, 34, 34, 0.541));
}

.mainData h3 {
  color: #3b3b3bea;
  margin-top: 12px;
}

/* Side Data */

.sideData {
  width: 50%;
  background: #fff;
  box-shadow: 2px 2px 25px rgba(0, 0, 0, 0.144);
  border-radius: 5px;
  padding: 20px 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.sideData .data {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  margin: 14px;
  color: #383838;
  background: #f2f2f2b9;
  border-radius: 6px;
  padding: 14px 10px;
  box-shadow: 2px 2px 8px rgba(0, 0, 0, 0.144);
}

.sideData .data h2 {
  font-size: 1.03em;
  font-weight: 500;
}

.sideData .data div {
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  font-size: 1.2em;
  margin-top: 8px;
}

.sideData .data div svg {
  width: 28px;
  height: 28px;
  margin-right: 6px;
}

.sideData .data div span {
  font-size: 0.8em;
  opacity: 0.9;
}

/* Media Queries */

@media screen and (max-width: 715px) {
  section {
    flex-direction: column;
  }
  .sideData {
    width: auto;
  }
}

/* Loading */

.loading {
  width: 100%;
  text-align: center;
  margin: 100px auto;
  font-size: 1.2em;
}
</style>
