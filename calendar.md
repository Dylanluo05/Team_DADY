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
    }

    .button-1:hover {
        background-color: #f2ba92;
        color: white;
    }
</style>

<form id = "calendar-form" onsubmit = "calendarAPI()"> 
    <label for = "year-1">Enter year 1:</label>
    <input id = "year-1" name = "year-1"><br>
    <label for = "year-2">Enter year 2:</label>
    <input id = "year-2" name = "year-2"><br>
    <label for = "month">Enter month:</label>
    <input id = "month" name = "month"><br>
    <label for = "day">Enter day:</label>
    <input id = "day" name = "day"><br>
    <input type = "submit" class = "button-1">
</form>

<script>
    function calendarAPI() {
        event.preventDefault();
        var calendarFormData = $("#calendar-form").serializeArray();
    }
</script>