<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Group Expense Tracker - 4 People</title>
<style>
  body { font-family: Arial, sans-serif; background: #f5f5f5; padding: 20px; max-width: 600px; margin: auto; }
  h2 { text-align: center; color: #2c3e50; }
  .card { background: white; padding: 15px; border-radius: 12px; margin-bottom: 15px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
  input, select, button { width: 100%; padding: 10px; margin: 8px 0; border-radius: 8px; border: 1px solid #ccc; box-sizing: border-box; }
  button { background: #27ae60; color: white; border: none; font-weight: bold; cursor: pointer; }
  button:hover { background: #219150; }
  .expense-item { display: flex; justify-content: space-between; padding: 8px; border-bottom: 1px solid #eee; }
  .summary { background: #3498db; color: white; }
  .delete { background: red; padding: 2px 8px; font-size: 12px; width: auto; }
</style>
</head>
<body>

<h2>💰 Group Expense Tracker</h2>

<div class="card">
  <h3>Add Expense</h3>
  <input type="date" id="date" required>
  <select id="person">
    <option value="Jasomay">Jasomay</option>
    <option value="Avik">Avik</option>
    <option value="Sypriya">Supriya</option>
    <option value="Santanu">Santanu</option>
  </select>
  <input type="text" id="category" placeholder="Category: Food, Rent, Travel">
  <input type="number" id="amount" placeholder="Amount ₹" required>
  <button onclick="addExpense()">Add Expense</button>
</div>

<div class="card">
  <h3>This Month's Expenses</h3>
  <div id="expenseList"></div>
</div>

<div class="card summary">
  <h3>📊 Monthly Summary</h3>
  <div id="summary"></div>
  <button onclick="monthlyReport()">Generate Monthly Report</button>
</div>

<script>
// 1. CHANGE THESE 4 NAMES
const PEOPLE = ["Jasomay", "Avik", "Supriya", "Santanu"];

let
