<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Employee Attendance</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        form {
            display: flex;
            flex-direction: column;
            max-width: 300px;
            margin: auto;
        }
        button {
            margin-top: 10px;
            padding: 8px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Employee Attendance</h1>

    <form id="attendanceForm">
        <label for="employeeName">Employee Name:</label>
        <input type="text" id="employeeName" required>

        <button type="button" onclick="markAttendance('in')">Clock In</button>
        <button type="button" onclick="markAttendance('out')">Clock Out</button>
    </form>

    <script>
        function markAttendance(type) {
            const employeeName = document.getElementById('employeeName').value;

            if (employeeName.trim() === '') {
                alert('Please enter the employee name.');
                return;
            }

            const timestamp = new Date().toLocaleString();
            const message = `${employeeName} ${type === 'in' ? 'clocked in' : 'clocked out'} at ${timestamp}`;

            alert(message);
            // Here, you can send the data to the server for storage and further processing.
        }
    </script>
</body>
</html>

