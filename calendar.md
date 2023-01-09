# Calendar
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.1/jquery.min.js"></script>
</head>

<style>
    .button-1 {
        height: 40px;
        width: 500px;
        background-color: white;
        color: #f2ba92;
        border: 2px solid #f2ba92;
        transition-duration: 0.4s;
        display: block;
        margin: auto;
    }

    .button-1:hover {
        background-color: #f2ba92;
        color: white;
    }

    .label-1 {
        display: block; 
        text-align: center;
    }

    .input-1 {
        height: 25px;
        width: 350px;
        border: none;
        background-color: lightgray;
        display: block;
        margin: auto;
    }
</style>

<form id = "calendar-form" onsubmit = "calendarAPI()"> 
    <label for = "year-1" class = "label-1">Enter year 1:</label><br>
    <input type = "number" id = "year-1" name = "year-1" class = "input-1"><br>
    <label for = "year-2" class = "label-1">Enter year 2:</label><br>
    <input type = "number" id = "year-2" name = "year-2" class = "input-1"><br>
    <label for = "month" class = "label-1">Enter month:</label><br>
    <input type = "number" id = "month" name = "month" class = "input-1"><br>
    <label for = "day" class = "label-1">Enter day:</label><br>
    <input type = "number" id = "day" name = "day" class = "input-1"><br>
    <input type = "submit" class = "button-1">
</form>

<script>
    const API_URL = 'https://frq.dtsivkovski.tk/api/calendar';

    function calendarAPI() {
        event.preventDefault();
        let expression = document.getElementById('expression-input').value;
        expression = expression.replace(/\^/g, 'POW');
        // Combine API URL with expression.
        fetch(`${API_URL}/${expression}`)
        .then(response => response.json())
        .then(data => {
            // Output data to table
            const table = document.getElementById('results-table');
            const row = table.insertRow(-1);
            const expressionCell = row.insertCell(0);
            const tokensCell = row.insertCell(1);
            const rpnCell = row.insertCell(2);
            const resultCell = row.insertCell(3);
            expressionCell.innerHTML = data.Expression;
            tokensCell.innerHTML = data.Tokens;
            rpnCell.innerHTML = data.RPN;
            resultCell.innerHTML = `<strong>${data.Result}</strong>`;
        });
    }
</script>