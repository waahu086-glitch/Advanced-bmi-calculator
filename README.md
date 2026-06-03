# Advanced-bmi-calculator
Bmi calculation made simple 
<!DOCTYPE html>
<html>
<head>
    <title>Loan EMI Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }

        .container {
            width: 350px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 10px;
        }

        input, button {
            width: 90%;
            padding: 10px;
            margin: 10px;
        }

        #result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>
<body>

<div class="container">
    <h2>Loan EMI Calculator</h2>

    <input type="number" id="loanAmount" placeholder="Loan Amount">

    <input type="number" id="interestRate" placeholder="Annual Interest Rate (%)">

    <input type="number" id="loanTerm" placeholder="Loan Term (Years)">

    <button onclick="calculateEMI()">Calculate EMI</button>

    <div id="result"></div>
</div>

<script>
function calculateEMI() {

    let P = parseFloat(document.getElementById("loanAmount").value);
    let annualRate = parseFloat(document.getElementById("interestRate").value);
    let years = parseFloat(document.getElementById("loanTerm").value);

    let r = annualRate / 12 / 100;
    let n = years * 12;

    let emi = (P * r * Math.pow(1 + r, n)) /
              (Math.pow(1 + r, n) - 1);

    let totalPayment = emi * n;
    let totalInterest = totalPayment - P;

    document.getElementById("result").innerHTML =
        "Monthly EMI: $" + emi.toFixed(2) + "<br>" +
        "Total Payment: $" + totalPayment.toFixed(2) + "<br>" +
        "Total Interest: $" + totalInterest.toFixed(2);
}
</script>

</body>
</html>
