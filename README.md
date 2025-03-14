<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aviator Game</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Header Section -->
    <header class="site-header">
        <div class="container">
            <h1>Aviator Game</h1>
            <nav>
                <ul class="nav-links">
                    <li><a href="#game">Game</a></li>
                    <li><a href="#leaderboard">Leaderboard</a></li>
                    <li><a href="#profile">Profile</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Main Game Section -->
    <main class="game-section" id="game">
        <div class="container">
            <div class="game-board">
                <!-- Withdraw and Deposit Buttons -->
                <div class="balance-actions">
                    <button id="deposit-btn" class="btn btn-success">Deposit</button>
                    <button id="withdraw-btn" class="btn btn-danger">Withdraw</button>
                </div>

                <!-- Balance Display -->
                <div class="balance-display">
                    Balance: $<span id="balance">1000</span>
                </div>

                <!-- Authentication Buttons (Sign Up and Log In) -->
                <div class="auth-buttons">
                    <button id="sign-up-btn" class="btn btn-primary">Sign Up</button>
                    <button id="log-in-btn" class="btn btn-secondary">Log In</button>
                </div>

                <h2>Current Multiplier: <span id="multiplier">1.00x</span></h2>
                <button id="start-game" class="btn btn-primary">Start Round</button>
                <button id="cash-out" class="btn btn-secondary" disabled>Cash Out</button>
                <div class="bet-controls">
                    <label for="bet-amount">Bet Amount:</label>
                    <input type="number" id="bet-amount" min="1" value="10">
                    <button id="place-bet" class="btn btn-success">Place Bet</button>
                </div>

                <!-- Preset Betting Buttons -->
                <div class="preset-bets">
                    <button class="preset-bet-btn" data-bet="10">$10</button>
                    <button class="preset-bet-btn" data-bet="50">$50</button>
                    <button class="preset-bet-btn" data-bet="100">$100</button>
                </div>

                <!-- Aviator Plane Animation -->
                <div class="plane-animation">
                    <img src="path/to/your/plane-image.png" alt="Aviator Plane" id="plane">
                </div>

                <p id="status-message"></p>
            </div>
        </div>
    </main>

    <!-- Leaderboard Section -->
    <section class="leaderboard-section" id="leaderboard">
        <div class="container">
            <h2>Leaderboard</h2>
            <table class="leaderboard-table">
                <thead>
                    <tr>
                        <th>Rank</th>
                        <th>Player</th>
                        <th>Score</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>1</td>
                        <td>Player1</td>
                        <td>500</td>
                    </tr>
                    <tr>
                        <td>2</td>
                        <td>Player2</td>
                        <td>450</td>
                    </tr>
                    <tr>
                        <td>3</td>
                        <td>Player3</td>
                        <td>400</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </section>

    <!-- Profile Section -->
    <section class="profile-section" id="profile">
        <div class="container">
            <h2>Profile</h2>
            <p>Welcome, <span id="username">Guest</span>!</p>
        </div>
    </section>

    <!-- Sign Up Modal -->
    <div id="sign-up-modal" class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <div id="step-1">
                <h2>Sign Up</h2>
                <label for="phone">Phone Number:</label>
                <input type="text" id="phone" placeholder="Enter your phone number" required>

                <label for="email">Email Address:</label>
                <input type="email" id="email" placeholder="Enter your email address" required>

                <label for="password">Password:</label>
                <input type="password" id="password" placeholder="Enter your password" required>

                <button id="submit-details" class="btn btn-primary">Submit</button>
            </div>

            <div id="step-2" style="display: none;">
                <h2>Verify Your Email</h2>
                <p>A verification code has been sent to your email.</p>
                <label for="verification-code">Verification Code:</label>
                <input type="text" id="verification-code" placeholder="Enter the code" required>

                <button id="verify-code" class="btn btn-primary">Verify</button>
            </div>
        </div>
    </div>

    <footer class="site-footer">
        <div class="container">
            <p>&copy; 2023 Aviator Game. All rights reserved.</p>
        </div>
    </footer>

    <script src="script.js"></script>
</body>
</html>  
/* styles.css */

/* General Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f9;
    color: #333;
    line-height: 1.6;
}

.container {
    width: 80%;
    margin: auto;
    max-width: 1200px;
}

/* Header */
.site-header {
    background-color: #333;
    color: #fff;
    padding: 1rem 0;
}

.site-header h1 {
    text-align: center;
    margin-bottom: 0.5rem;
}

.nav-links {
    display: flex;
    justify-content: center;
    list-style: none;
}

.nav-links li {
    margin: 0 1rem;
}

.nav-links a {
    color: #fff;
    text-decoration: none;
    font-weight: bold;
}

.nav-links a:hover {
    text-decoration: underline;
}

/* Game Section */
.game-section {
    padding: 2rem 0;
    text-align: center;
}

.game-board {
    background-color: #fff;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    position: relative;
}

/* Balance Actions (Withdraw and Deposit Buttons) */
.balance-actions {
    position: absolute;
    top: 10px;
    right: 20px;
    display: flex;
    gap: 10px;
}

/* Balance Display */
.balance-display {
    position: absolute;
    top: 50px;
    right: 20px;
    font-size: 1.2rem;
    font-weight: bold;
    color: #3498db;
}

/* Authentication Buttons (Sign Up and Log In) */
.auth-buttons {
    position: absolute;
    top: 10px;
    left: 20px;
    display: flex;
    gap: 10px;
}

/* Current Multiplier */
#multiplier {
    color: #e74c3c;
    font-size: 1.5rem;
}

.bet-controls {
    margin-top: 1rem;
}

.bet-controls label {
    margin-right: 0.5rem;
}

.bet-controls input {
    padding: 0.5rem;
    width: 100px;
    margin-right: 0.5rem;
}

/* Preset Betting Buttons */
.preset-bets {
    margin-top: 1rem;
}

.preset-bet-btn {
    padding: 0.5rem 1rem;
    margin: 0 0.5rem;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1rem;
    background-color: #3498db;
    color: #fff;
}

.preset-bet-btn:hover {
    background-color: #2980b9;
}

/* Buttons */
.btn {
    padding: 0.5rem 1rem;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1rem;
}

.btn-primary {
    background-color: #3498db;
    color: #fff;
}

.btn-primary:hover {
    background-color: #2980b9;
}

.btn-secondary {
    background-color: #e74c3c;
    color: #fff;
}

.btn-secondary:hover {
    background-color: #c0392b;
}

.btn-success {
    background-color: #2ecc71;
    color: #fff;
}

.btn-success:hover {
    background-color: #27ae60;
}

.btn-danger {
    background-color: #e74c3c;
    color: #fff;
}

.btn-danger:hover {
    background-color: #c0392b;
}

/* Aviator Plane Animation */
.plane-animation {
    position: relative;
    height: 200px;
    overflow: hidden;
}

#plane {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    transition: bottom 0.5s ease-in-out;
}

/* Leaderboard Section */
.leaderboard-section {
    padding: 2rem 0;
    text-align: center;
}

.leaderboard-table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 1rem;
}

.leaderboard-table th,
.leaderboard-table td {
    padding: 0.5rem;
    border: 1px solid #ddd;
}

.leaderboard-table th {
    background-color: #f4f4f9;
}

/* Profile Section */
.profile-section {
    padding: 2rem 0;
    text-align: center;
}

/* Footer */
.site-footer {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 1rem 0;
    margin-top: 2rem;
}

/* Modal Styles */
.modal {
    display: none; /* Hidden by default */
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent background */
}

.modal-content {
    background-color: #fff;
    margin: 10% auto;
    padding: 2rem;
    border: 1px solid #888;
    width: 400px;
    max-width: 90%;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    text-align: center;
}

.close {
    color: #aaa;
    float: right;
    font-size: 2rem;
    font-weight: bold;
    cursor: pointer;
}

.close:hover,
.close:focus {
    color: #000;
    text-decoration: none;
    cursor: pointer;
}

.modal-content form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.modal-content input {
    padding: 0.5rem;
    font-size: 1rem;
    border: 1px solid #ccc;
    border-radius: 4px;
}
// script.js

let currentMultiplier = 1.00;
let betAmount = 0;
let balance = 1000;
let roundActive = false;
let intervalId;

// DOM Elements
const multiplierDisplay = document.getElementById('multiplier');
const startGameButton = document.getElementById('start-game');
const cashOutButton = document.getElementById('cash-out');
const placeBetButton = document.getElementById('place-bet');
const betInput = document.getElementById('bet-amount');
const statusMessage = document.getElementById('status-message');
const balanceDisplay = document.getElementById('balance');
const plane = document.getElementById('plane');
const depositButton = document.getElementById('deposit-btn');
const withdrawButton = document.getElementById('withdraw-btn');
const signUpButton = document.getElementById('sign-up-btn');
const logInButton = document.getElementById('log-in-btn');

// Modal Elements
const signUpModal = document.getElementById('sign-up-modal');
const closeModalButton = document.querySelector('.close');
const step1 = document.getElementById('step-1');
const step2 = document.getElementById('step-2');
const submitDetailsButton = document.getElementById('submit-details');
const verifyCodeButton = document.getElementById('verify-code');

// Function to update the balance display
function updateBalance(amount) {
    balance += amount;
    balanceDisplay.textContent = balance.toFixed(2);
}

// Show Sign Up Modal
signUpButton.addEventListener('click', () => {
    signUpModal.style.display = 'block';
});

// Close Sign Up Modal
closeModalButton.addEventListener('click', () => {
    signUpModal.style.display = 'none';
    step1.style.display = 'block'; // Reset to step 1
    step2.style.display = 'none';
});

// Handle Step 1 Submission
submitDetailsButton.addEventListener('click', () => {
