<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="header" elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
        <q-toolbar-title class="demo"> دفتر کارگشا (دمو) </q-toolbar-title>

        <div class="header-icons">
          <q-btn flat dense round icon="search" aria-label="search" />

          <div class="fiscal-year-container">
            <span class="fiscal-year">Fiscal Year: 1401</span>
            <div class="account">
              <q-btn flat dense round icon="account_circle" />
            </div>
          </div>
          <q-btn flat dense round icon="settings" aria-label="settings" />
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <div class="dashboard-header" @click="whenDashboardClicked">
        <q-list>
          <q-item-label clickable header class="header-label">
            <q-icon name="dashboard" class="dashboard"></q-icon>
            <span>Dashboard</span>
          </q-item-label>
        </q-list>
      </div>
      <div class="q-pa-md">
        <q-input
          square
          outlined
          dense
          v-model="text"
          label="Search"
          color="blue"
        ></q-input>
      </div>
      <div class="side-bar">
        <q-list>
          <q-expansion-item
            active-class="tab-active"
            icon="shop_2"
            label="Sales and Purchase"
            class="sub-item"
          >
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="content_paste"></q-icon>
              </q-item-section>
              <q-item-section>Proformas</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="receipt_long"></q-icon>
              </q-item-section>
              <q-item-section>Invoices</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="shopping_cart"></q-icon>
              </q-item-section>
              <q-item-section>Purchase</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="turn_left"></q-icon>
              </q-item-section>
              <q-item-section>Return from Sales</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="subject"></q-icon>
              </q-item-section>
              <q-item-section>Sales Type</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="subject"></q-icon>
              </q-item-section>
              <q-item-section>Purchase Type</q-item-section>
            </q-item>
          </q-expansion-item>

          <q-expansion-item
            icon="credit_card"
            label="Receipt and Payment"
            class="sub-item"
          >
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_downward"></q-icon>
              </q-item-section>
              <q-item-section>Receipts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_upward"></q-icon>
              </q-item-section>
              <q-item-section>Payments</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="attach_money"></q-icon>
              </q-item-section>
              <q-item-section>Bills</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="swap_horiz"></q-icon>
              </q-item-section>
              <q-item-section>Transfer Money</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="subject"></q-icon>
              </q-item-section>
              <q-item-section>Bank Accounts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="monetization_on"></q-icon>
              </q-item-section>
              <q-item-section>Cashs</q-item-section>
            </q-item>
          </q-expansion-item>

          <q-expansion-item
            icon="receipt_long"
            label="Accounting"
            class="sub-item"
          >
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_downward"></q-icon>
              </q-item-section>
              <q-item-section>Receipts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_upward"></q-icon>
              </q-item-section>
              <q-item-section>Payments</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="attach_money"></q-icon>
              </q-item-section>
              <q-item-section>Bills</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="swap_horiz"></q-icon>
              </q-item-section>
              <q-item-section>Transfer Money</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="subject"></q-icon>
              </q-item-section>
              <q-item-section>Bank Accounts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="monetization_on"></q-icon>
              </q-item-section>
              <q-item-section>Cashs</q-item-section>
            </q-item>
          </q-expansion-item>

          <q-expansion-item icon="account_box" label="Payroll" class="sub-item">
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_downward"></q-icon>
              </q-item-section>
              <q-item-section>Receipts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_upward"></q-icon>
              </q-item-section>
              <q-item-section>Payments</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="attach_money"></q-icon>
              </q-item-section>
              <q-item-section>Bills</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="swap_horiz"></q-icon>
              </q-item-section>
              <q-item-section>Transfer Money</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="subject"></q-icon>
              </q-item-section>
              <q-item-section>Bank Accounts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="monetization_on"></q-icon>
              </q-item-section>
              <q-item-section>Cashs</q-item-section>
            </q-item>
          </q-expansion-item>
          <q-expansion-item icon="home" label="Warehousing" class="sub-item">
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_downward"></q-icon>
              </q-item-section>
              <q-item-section>Receipts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_upward"></q-icon>
              </q-item-section>
              <q-item-section>Payments</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="attach_money"></q-icon>
              </q-item-section>
              <q-item-section>Bills</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="swap_horiz"></q-icon>
              </q-item-section>
              <q-item-section>Transfer Money</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="subject"></q-icon>
              </q-item-section>
              <q-item-section>Bank Accounts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="monetization_on"></q-icon>
              </q-item-section>
              <q-item-section>Cashs</q-item-section>
            </q-item>
          </q-expansion-item>
          <q-expansion-item icon="group" label="Organization" class="sub-item">
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_downward"></q-icon>
              </q-item-section>
              <q-item-section>Receipts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_upward"></q-icon>
              </q-item-section>
              <q-item-section>Payments</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="attach_money"></q-icon>
              </q-item-section>
              <q-item-section>Bills</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="swap_horiz"></q-icon>
              </q-item-section>
              <q-item-section>Transfer Money</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="subject"></q-icon>
              </q-item-section>
              <q-item-section>Bank Accounts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="monetization_on"></q-icon>
              </q-item-section>
              <q-item-section>Cashs</q-item-section>
            </q-item>
          </q-expansion-item>
          <q-expansion-item icon="info" label="Base Info" class="sub-item">
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_downward"></q-icon>
              </q-item-section>
              <q-item-section>Receipts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_upward"></q-icon>
              </q-item-section>
              <q-item-section>Payments</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="attach_money"></q-icon>
              </q-item-section>
              <q-item-section>Bills</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="swap_horiz"></q-icon>
              </q-item-section>
              <q-item-section>Transfer Money</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="subject"></q-icon>
              </q-item-section>
              <q-item-section>Bank Accounts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="monetization_on"></q-icon>
              </q-item-section>
              <q-item-section>Cashs</q-item-section>
            </q-item>
          </q-expansion-item>
          <q-expansion-item
            icon="bar_chart"
            label="Reports"
            class="sub-item"
            id="reports"
          >
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_downward"></q-icon>
              </q-item-section>
              <q-item-section>Receipts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="arrow_upward"></q-icon>
              </q-item-section>
              <q-item-section>Payments</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="attach_money"></q-icon>
              </q-item-section>
              <q-item-section>Bills</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="swap_horiz"></q-icon>
              </q-item-section>
              <q-item-section>Transfer Money</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="subject"></q-icon>
              </q-item-section>
              <q-item-section>Bank Accounts</q-item-section>
            </q-item>
            <q-item clickable>
              <q-item-section avatar class="item-section">
                <q-icon color="accent" name="monetization_on"></q-icon>
              </q-item-section>
              <q-item-section>Cashs</q-item-section>
            </q-item>
          </q-expansion-item>
          <q-separator inset />
          <div class="settings-header" @click="whenDashboardClicked">
            <q-list>
              <q-item-label clickable header class="setting-label">
                <q-icon name="settings" class="settings"></q-icon>
                <span class="setting">Dashboard</span>
              </q-item-label>
            </q-list>
          </div>
        </q-list>
      </div>
    </q-drawer>

    <q-page-container>
      <div class="q-pa-md row items-center q-gutter-md cards">
        <q-card class="proforma-q-card">
          <q-card-section class="my-card-section">
            <q-icon name="content_paste" class="proforma-card"></q-icon>
            {{ createProforma }}
          </q-card-section>
        </q-card>
        <q-card class="invoice-q-card">
          <q-card-section class="my-card-section">
            <q-icon name="content_paste" class="proforma-card"></q-icon>
            {{ createInvoice }}
          </q-card-section>
        </q-card>
        <q-card class="payment-q-card">
          <q-card-section class="my-card-section">
            <q-icon name="content_paste" class="proforma-card"></q-icon>
            {{ createPayment }}
          </q-card-section>
        </q-card>
        <q-card class="receipt-q-card">
          <q-card-section class="my-card-section">
            <q-icon name="content_paste" class="proforma-card"></q-icon>
            {{ createReceipt }}
          </q-card-section>
        </q-card>
      </div>

      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
// Open & Close Drawer
const name = "MainLayout";
const leftDrawerOpen = ref(false);
const toggleLeftDrawer = () => {
  leftDrawerOpen.value = !leftDrawerOpen.value;
};

// When Dashboard Header Clicked
const whenDashboardClicked = () => {
  window.open("https://my.landa-sme.ir/home/index");
};

// Drawer Search Bar
const text = ref("");

const createProforma = ref("Create Proforma");
const createInvoice = ref("Create Invoice");
const createPayment = ref("Create Payment");
const createReceipt = ref("Create Receipt");
</script>
