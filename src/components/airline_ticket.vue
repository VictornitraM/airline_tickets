<template>
  <b-container
    class="pt-4"
    :style="{
      '--bg-color-top': bgColorTop,
      '--font-size-span': valueSpan,
      '--font-size-p': valueP,
      '--font-color': fontColor,
      '--passenger-name': passengerName,
    }"
  >
    <div class="ticket basic">
      <p>Admit One</p>
    </div>

    <b-row>
      <b-col md="12">
        <h2>Airline Ticket - Live UI Updates</h2>
      </b-col>
    </b-row>
    <b-row>
      <b-col md="2"></b-col>
      <b-col md="4">
        <div id="inputs">
          <b-row>
            <b-col md="6">
              <label for="colorPicker">Pick a new header color</label>
              <b-form-input
                id="colorPicker"
                type="color"
                :value="bgColorTop"
                v-model="bgColorTop"
              >
              </b-form-input>
            </b-col>

            <b-col md="6">
              <label for="fontColorPicker">Pick a new font color</label>
              <b-form-input
                id="fontColorPicker"
                type="color"
                :value="fontColor"
                v-model="fontColor"
              >
              </b-form-input>
            </b-col>
          </b-row>

          <b-row class="mt-4">
            <b-col md="12">
              <label for="nameInput">Change the passengers name:</label>
              <b-form-input
                v-model="passengerName"
                id="nameInput"
                type="text"
              ></b-form-input>
            </b-col>
          </b-row>
          <b-row class="mt-4">
            <b-col md="12">
              <label for="fontSize-p"
                >Label font size (e.g. "Flight", "Gate")</label
              >
              <b-form-input
                v-model="valueSpan"
                id="fontSize-p"
                type="range"
                name="vol1"
                min="13"
                max="20"
                step="1"
              ></b-form-input>
              <div>Value: {{ valueSpan }}</div>
            </b-col>
            <b-col md="12">
              <label for="fontSize-span"
                >Info font size (e.g. "AA2005", "B3")</label
              >
              <b-form-input
                v-model="valueP"
                id="fontSize-span"
                type="range"
                name="vol2"
                min="11"
                max="20"
                step="1"
              ></b-form-input>
              <div>Value: {{ valueP }}</div>
            </b-col>
          </b-row>
        </div>
      </b-col>

      <b-col md="4">
        <div class="ticket airline">
          <div class="top">
            <h1>boarding pass</h1>
            <div class="big">
              <p class="from">BWI</p>
              <p class="to"><i class="fas fa-arrow-right"></i> SAN</p>
            </div>
            <div class="top--side">
              <i class="fas fa-plane"></i>
              <p>Baltimore</p>
              <p>San Diego</p>
            </div>
          </div>
          <div class="bottom">
            <div class="column">
              <div class="row row-1">
                <p><span>Flight</span>AA2005</p>
                <p class="row--right"><span>Gate</span>B3</p>
              </div>
              <div class="row row-2">
                <p><span>Boards</span>10:25 AM</p>
                <p class="row--center"><span>Departs</span>11:00 AM</p>
                <p class="row--right"><span>Arrives</span>1:05 PM</p>
              </div>
              <div class="row row-3">
                <p><span>Passenger</span>{{ passengerName }}</p>
                <p class="row--center"><span>Seat</span>11E</p>
                <p class="row--right"><span>Group</span>3</p>
              </div>
            </div>
            <div class="bar--code"></div>
          </div>
        </div>
      </b-col>
      <b-col md="2"></b-col>
    </b-row>
    <div class="info">
      <p>
        Based on
        <a
          href="https://dribbble.com/shots/11399236-Boarding-Pass"
          target="_blank"
          >this</a
        >
        Dribbble from Barna Erdei
      </p>
    </div>
  </b-container>
</template>

<script>
export default {
  name: "AirlineTicket",
  data() {
    return {
      bgColorTop: "#ffcc05",
      fontColor: "#1e1e17",
      passengerName: "Jesus Ramirez",
      valueP: 13,
      valueSpan: 11,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap");
@import url(https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css);

$container: #e0e2e8;
$topbg: #ffcc05;
$bottombg: #fff;
$font: "Open Sans", sans-serif;
$grey: #6c6c6c;

body,
p,
h1,
h2 {
  margin: 0;
  padding: 0;
  font-family: $font;
  text-align: center;
}

body {
  background-color: $container !important;
}

.container {
  background: $container;
  position: relative;
  width: 100%;
  height: 100vh;
  .ticket {
    position: relative;
    top: 60%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  .basic {
    display: none;
  }
}

.airline {
  display: block;
  height: 575px;
  width: 270px;
  box-shadow: 5px 5px 30px rgba(0, 0, 0, 0.3);
  border-radius: 25px;
  z-index: 3;
  .top {
    height: 220px;
    background: var(--bg-color-top);
    border-top-right-radius: 25px;
    border-top-left-radius: 25px;
    h1 {
      text-transform: uppercase;
      font-size: 12px;
      letter-spacing: 2;
      text-align: center;
      position: absolute;
      top: 30px;
      left: 50%;
      transform: translateX(-50%);
    }
  }
  .bottom {
    height: 355px;
    background: $bottombg;
    border-bottom-right-radius: 25px;
    border-bottom-left-radius: 25px;
  }
}

.top {
  .big {
    position: absolute;
    top: 100px;
    font-size: 65px;
    font-weight: 700;
    line-height: 0.8;
    .from {
      color: var(--bg-color-top);
      text-shadow: -1px 0 #000, 0 1px #000, 1px 0 #000, 0 -1px #000;
    }
    .to {
      position: absolute;
      left: 32px;
      font-size: 35px;
      display: flex;
      flex-direction: row;
      align-items: center;
      i {
        margin-top: 5px;
        margin-right: 10px;
        font-size: 15px;
      }
    }
  }
  &--side {
    position: absolute;
    right: 35px;
    top: 110px;
    text-align: right;
    i {
      font-size: 25px;
      margin-bottom: 18px;
    }
    p {
      font-size: 10px;
      font-weight: 700;
    }
    p + p {
      margin-bottom: 8px;
    }
  }
}
.bottom {
  p {
    display: flex;
    flex-direction: column;
    font-size: calc(var(--font-size-p) * 1px);
    font-weight: 700;
    color: var(--font-color);
    span {
      font-weight: 400;
      font-size: calc(var(--font-size-span) * 1px);
      color: $grey;
    }
  }
  .column {
    margin: 0 auto;
    width: 80%;
    padding: 2rem 0;
  }
  .row {
    display: flex;
    justify-content: space-between;
    &--right {
      text-align: right;
    }
    &--center {
      text-align: center;
    }
    &-2 {
      margin: 30px 0 60px 0;
      position: relative;
      &::after {
        content: "";
        position: absolute;
        width: 100%;
        bottom: -30px;
        left: 0;
        background: #000;
        height: 1px;
      }
    }
  }
}

.bottom {
  p {
    width: auto;
  }
  .bar--code {
    height: 50px;
    width: 80%;
    margin: 0 auto;
    position: relative;
    &::after {
      content: "";
      position: absolute;
      width: 6px;
      height: 100%;
      background: #000;
      top: 0;
      left: 0;
      box-shadow: 10px 0 #000, 30px 0 #000, 40px 0 #000, 67px 0 #000,
        90px 0 #000, 100px 0 #000, 180px 0 #000, 165px 0 #000, 200px 0 #000,
        210px 0 #000, 135px 0 #000, 120px 0 #000;
    }
    &::before {
      content: "";
      position: absolute;
      width: 3px;
      height: 100%;
      background: #000;
      top: 0;
      left: 11px;
      box-shadow: 12px 0 #000, -4px 0 #000, 45px 0 #000, 65px 0 #000,
        72px 0 #000, 78px 0 #000, 97px 0 #000, 150px 0 #000, 165px 0 #000,
        180px 0 #000, 135px 0 #000, 120px 0 #000;
    }
  }
}

.info {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: 30px;
  font-size: 14px;
  text-align: center;
  z-index: 1;
  a {
    text-decoration: none;
    color: #000;
    background: var(--bg-color-top);
  }
}
</style>
