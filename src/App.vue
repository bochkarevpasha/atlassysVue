<template>
  <div class="app">
    <nav class="navbar">
      <div class="logo">
        <!-- <img src="assets/Logo.png" alt=""> -->
      </div>

      <div class="navbar-items">
        <div v-for="item in navbarItems" :key="item.link" class="navbar-item">
          <img class="navbar-icon" :src="item.icon" alt="">
          <a 
            href="#" 
            class="navbar-link" 
            :class="{ 'is-navabar-link-active': item.active }">{{ item.text }}
          </a>
        </div>
      </div>
    </nav>

    <header class="header">
      <h1 class="header-title">Setting</h1>

      <div class="header-items">
        <div class="header-item search-field">
          <img class="header-icon" src="./assets/icons/magnifying-glass.svg" alt="">
          <input type="text" class="header-input" placeholder="Search for something">
        </div>
        <div class="header-item header__button">
          <img class="header-icon" src="./assets/icons/settings1.svg" alt="">
        </div>
        <div class="header-item header__button">
          <img class="header-icon" src="./assets/icons/notification.svg" alt="">
        </div>
        <img class="header__profile-picture" src="./assets/profile-picture.png" alt="">
      </div>
    </header>

    <header class="mobile-header">
      <div class="mobile-header-items">
        <div class="header-burger">
          <div></div>
          <div></div>
          <div></div>
        </div>
        <h1 class="header-title">Setting</h1>
        <img class="header__profile-picture" src="./assets/profile-picture.png" alt="">
      </div>
      <div class="header-item search-field">
        <img class="header-icon" src="./assets/icons/magnifying-glass.svg" alt="">
        <input type="text" class="header-input" placeholder="Search for something">
      </div>
    </header>

    <main class="main">
      <div class="setting">
        <div class="setting__header">
          <p 
            v-for="title in settingHeaderTitles" 
            :key="title" 
            class="setting__header-title" 
            :class="{ 'is-link-active': title === 'Edit Profile' }"
            >
            {{ title }}
          </p>
        </div>

        <div class="setting__content">
          <div class="setting__profile-img-container">
            <img class="setting__profile-img" src="./assets/profile-picture.png" alt="">
            <div class="setting__profile-img-edit">
              <img class="setting__profile-img-edit-icon" src="./assets/icons/pencil.svg" alt="">
            </div>
          </div>
          <div class="setting__content-column">
            <div class="setting__content-item">
                <p class="setting__content-item-title">
                    Your Name
                </p>
                <input type="text" class="setting__content-item-input" placeholder="Charlene Reed ">
            </div>
            <div class="setting__content-item">
                <p class="setting__content-item-title">
                    Email
                </p>
                <input type="email" class="setting__content-item-input" placeholder="charlenereed@gmail.com">
            </div>
            <div class="setting__content-item">
                <p class="setting__content-item-title">
                    Date of Birth
                </p>
                <input type="date" class="setting__content-item-input" placeholder="25 January 1990" id="dateInput">
                <input type="text" id="formattedDateInput" class="setting__content-item-input" readonly placeholder="25 January 1990">
                <img src="./assets/icons/arrow-down.svg" alt="Calendar" class="custom-calendar-icon" onclick="document.getElementById('dateInput').showPicker();">
            </div>
            <div class="setting__content-item">
                <p class="setting__content-item-title">
                    Permanent Address
                </p>
                <input type="text" class="setting__content-item-input" placeholder="San Jose, California, USA">
            </div>
            <div class="setting__content-item">
                <p class="setting__content-item-title">
                    Postal Code
                </p>
                <input type="number" class="setting__content-item-input" placeholder="45962">
            </div>
          </div>
          <div class="setting__content-column">
              <div class="setting__content-item">
                  <p class="setting__content-item-title">
                      User Name
                  </p>
                  <input type="text" class="setting__content-item-input" placeholder="Charlene Reed">
              </div>
              <div class="setting__content-item">
                  <p class="setting__content-item-title">
                      Password
                  </p>
                  <input type="password" class="setting__content-item-input" placeholder="**********">
              </div>
              <div class="setting__content-item">
                  <p class="setting__content-item-title">
                      Present Address
                  </p>
                  <input type="text" class="setting__content-item-input" placeholder="San Jose, California, USA">
              </div>
              <div class="setting__content-item">
                  <p class="setting__content-item-title">
                      City
                  </p>
                  <input type="text" class="setting__content-item-input" placeholder="San Jose">
              </div>
              <div class="setting__content-item">
                  <p class="setting__content-item-title">
                      Country
                  </p>
                  <input type="text" class="setting__content-item-input" placeholder="USA">
              </div>

              <button class="setting__content-item-save-btn">
                  Save
              </button>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

import dashboardIcon from './assets/icons/home.svg';
import transferIcon from './assets/icons/transfer.svg';
import userIcon from './assets/icons/user.svg';
import economicInvestmentIcon from './assets/icons/economic-investment.svg';
import creditCardIcon from './assets/icons/credit-card.svg';
import loanIcon from './assets/icons/loan.svg';
import serviceIcon from './assets/icons/service.svg';
import econometricIcon from './assets/icons/econometrics.svg';
import settingIcon from './assets/icons/settings.svg';


const navbarItems = ref([
  { 
    icon: dashboardIcon, 
    text: 'Dashboard', 
    link: '#', 
    active: false 
  },
  { 
    icon: transferIcon, 
    text: 'Transactions', 
    link: '#', 
    active: false 
  },
  { 
    icon: userIcon, 
    text: 'Accounts', 
    link: '#', 
    active: false 
  },
  { 
    icon: economicInvestmentIcon, 
    text: 'Investments', 
    link: '#', 
    active: false 
  },
  { 
    icon: creditCardIcon, 
    text: 'Credit Cards', 
    link: '#',
    active: false 
  },
  { 
    icon: loanIcon, 
    text: 'Loans', 
    link: '#', 
    active: false 
  },
  { 
    icon: serviceIcon, 
    text: 'Services', 
    link: '#', 
    active: false 
  },
  { 
    icon: econometricIcon, 
    text: 'My Privileges', 
    link: '#', 
    active: false 
  },
  { 
    icon: settingIcon, 
    text: 'Setting', 
    link: '#', 
    active: true 
  },
]);

const settingHeaderTitles = ref(['Edit Profile', 'Preferences', 'Security']);

const settingContentItems = ref([
  { 
    title: 'Your Name', 
    type: 'text', 
    placeholder: 'Charlene Reed'  
  },
  { 
    title: 'Email', 
    type: 'email', 
    placeholder: 'charlenereed@gmail.com' 
  },
  { 
    title: 'Date of Birth', 
    type: 'date', 
    placeholder: '25 January 1990' 
  },
  { 
    title: 'Permanent Address', 
    type: 'text', 
    placeholder: 'San Jose, California, USA' 
  },
  { 
    title: 'Postal Code', 
    type: 'number', 
    placeholder: '45962' 
  },
  { 
    title: 'User Name', 
    type: 'text', 
    placeholder: 'Charlene Reed' 
  },
  { 
    title: 'Password', 
    type: 'password', 
    placeholder: '**********' 
  },
  { 
    title: 'Present Address', 
    type: 'text', 
    placeholder: 'San Jose, California, USA' 
  },
  { 
    title: 'City', 
    type: 'text', 
    placeholder: 'San Jose' 
  },
  { 
    title: 'Country', 
    type: 'text', 
    placeholder: 'USA' 
  },
]);

const dateInput = ref('');
const formattedDate = ref('');

const formatDate = () => {
  const date = new Date(dateInput.value);
  if (!isNaN(date.getTime())) {
    const day = date.getDate();
    const month = date.toLocaleString('default', { month: 'long' });
    const year = date.getFullYear();
    formattedDate.value = `${day} ${month} ${year}`;
  }
};

const showDatePicker = () => {
  document.getElementById('dateInput').showPicker();
};
</script>

<style scoped>
imp
.app {
    /* padding: 50px; */
    width: 100%;
    height: 100%;
}

input {
    color: #718EBF;
    font-size: 15px;
    line-height: 18.15px;
    font-family: 'Inter-regular';
    font-weight: 400;

    @media (max-width: 960px) {
        font-size: 13px;
    }
}

input::placeholder {
    color: #718EBF;
}

.header {
    width: calc(100% - 249px);
    position: fixed;
    display: flex;
    justify-content: space-between;
    align-items: center;
    right: 0px;
    padding: 40px;
    /* padding: 0 20px; */
    background-color: #fff;
    border-bottom: 1px solid #E6EFF5;
    z-index: 100;
    @media (max-width: 960px) {
        display: none;
    }
}

.mobile-header {
    position: fixed;
    border-bottom: 1px solid #E6EFF5;
    background-color: #fff;
    padding: 30px;
    width: 100%;
    display: none;
    z-index: 100;
    @media (max-width: 960px) {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        gap: 30px;
    }
}

.mobile-header-items {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.header-burger {
    display: flex;
    flex-direction: column;
    gap: 3px;
    padding: 20px;
    border-radius: 50%;
}

.header-burger:hover{
    cursor: pointer;
    background-color: #F5F7FA;
    transition: all .2s ease;
}

.header-burger div {
    height: 2px;
    width: 20px;
    background-color: #343C6A;
    border-radius: 5px;
}

.header-title {
    display: block;
    font-family: 'Inter-semibold';
    color: #343C6A;
    font-size: 28px;
    @media (max-width: 960px) {
        font-size: 20px;
    }
}

.header__button {
    @media (max-width: 960px) {
        display: none;
    }
}

.header-items {
    display: flex;
    gap: 30px;
    @media (max-width: 960px) {
        flex-wrap: wrap;
    }
}

.header-item {
    background-color: #F5F7FA;
    padding: 15px;
    border-radius: 50%;
}

.header-icon {
    width: 25px;
    height: 25px;
}

.header-input {
    background-color: #F5F7FA;
}

.header__profile-picture {
    display: block;
    width: 60px;
    height: 60px;
    border-radius: 50%;

    @media (max-width: 960px) {
        justify-self: end;
        width: 35px;
        height: 35px;
    }
}

.search-field {
    display: flex;
    align-items: center;
    gap: 10px;
    border-radius: 50px;
    padding: 15px 30px;
    font-family: 'Inter-regular';

    @media (max-width: 960px) {
        bottom: 0;
        width: 100%;
        order: 3;
    }
}

.navbar {
    width: 249px;
    padding: 40px 25px 40px 40px;
    background-color: #fff;
    height: 100%;
    display: flex;
    flex-direction: column;
    gap: 50px;
    position: fixed;
    border-right: 1px solid #E6EFF5;
    z-index: 100;
    @media (max-width: 960px) {
        display: none;
    }
}

.navbar-link {
    color: #B1B1B1;
}

.is-navabar-link-active {
    color: #1814F3;
}

.logo {
    height: 60px;
    width: 100%;
    background: url('./assets/Logo.svg');
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
}

.logo img {
    display: flex;
    align-self: center;
}

.navbar-items {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.navbar-item {
    padding: 10px;
    display: flex;
    align-items: center;
    gap: 15px;
    font-size: 18px;
    line-height: 21.78px;
}

.main {
    width: calc(100% - 309px);

    margin: 30px;
    padding: 30px;
    border-radius: 25px;
    background-color: #fff;
    position: absolute;
    top: 141px;
    left: 249px;

    @media (max-width: 960px) {
        width: calc(100% - 60px);
        top: 206px;
        left: 0;

    }
}

.setting__header {
    width: 100%;
    display: flex;
    gap: 30px;
    border-bottom: 1px solid #F4F5F7;
    @media (max-width: 960px) {
        gap: 10px;
        justify-content: center;
    }
}

.setting__header-title {
    color: #718EBF;
    font-size: 16px;
    padding: 15px;
    @media (max-width: 960px) {
        font-size: 13px;
        padding: 10px;
    }
}

.is-link-active {
    position: relative;
    color: #1814F3;
}

.setting__content {
    width: 100%;

    margin-top: 50px;
    display: flex;
    gap: 30px;
    @media (max-width: 960px) {
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
    }
}

.setting__content-column {
    width: 100%;

    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    gap: 20px;
}

.setting__content-item {
    position: relative;
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.setting__content-item-title {
    color: #232323;
    font-family: 'Inter-regular';
    font-size: 16px;
    line-height: 19.36px;
    @media (max-width: 960px) {
        font-size: 13px;
    }
}

.setting__content-item-input {
    border: 1px solid #DFEAF2;
    padding: 15px;
    border-radius: 10px;
}

.setting__content-item-save-btn {
    align-self: flex-end;
    width: 190px;
    padding: 15px;
    border-radius: 10px;
    background-color: #1814F3;
    color: #fff;
    font-family: 'Inter-medium';
    font-size: 18px;
    line-height: 21.78px;
    @media (max-width: 960px) {
        width: 100%;
        font-size: 15px;
    }
}

.setting__profile-img-container {
    width: 130px;
    height: 130px;
    display: flex;
    position: relative;
    @media (max-width: 960px) {
        justify-self: center;
        width: 170px;
        height: 170px;
    }
}

.setting__profile-img-edit {
    background-color: #1814F3;
    height: 38px;
    border-radius: 50%;
    padding: 10px;
    position: absolute;
    cursor: pointer;
    bottom: 20px;
    right: 0;
}

.setting__profile-img {
    width: 130px;
    border-radius: 50%;
    @media (max-width: 960px) {
        width: 170px;
    }
}

input[type="date"]::-webkit-calendar-picker-indicator {
    opacity: 0;
    z-index: 3;
}

#dateInput {
    display: none;
}

.custom-calendar-icon {
    position: absolute;
    right: 17px;
    top: 70%;
    transform: translateY(-50%);
    cursor: pointer;
}
</style>