<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Salary Details</title>
</head>
<body>
    <header>
        <h1>Salary Details</h1>
    </header>
    <main>
        <div id="salary-details">
            <h2>Employee Salary Details</h2>
            <table id="salary-table">
                <tr>
                    <th>Employee ID</th>
                    <th>Employee Name</th>
                    <th>Basic Salary</th>
                    <th>HRA</th>
                    <th>TA</th>
                    <th>Total Salary</th>
                </tr>
                <!-- Table rows will be generated dynamically -->
            </table>
        </div>
    </main>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
}

header {
    background-color: #333;
    color: #fff;
    padding: 20px;
    text-align: center;
}

#salary-details {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
}

table {
    border-collapse: collapse;
    width: 50%;
}

th, td {
    border: 1px solid #ddd;
    padding: 10px;
    text-align: left;
}

th {
    background-color: #333;
    color: #fff;
}
// Sample salary data
const salaryData = [
    { employeeId: 1, employeeName: 'John Doe', basicSalary: 50000, hra: 10000, ta: 5000 },
    { employeeId: 2, employeeName: 'Jane Doe', basicSalary: 60000, hra: 12000, ta: 6000 },
    { employeeId: 3, employeeName: 'Bob Smith', basicSalary: 70000, hra: 14000, ta: 7000 }
];

// Function to calculate total salary
function calculateTotalSalary(salary) {
    return salary.basicSalary + salary.hra + salary.ta;
}

// Function to display salary details
function displaySalaryDetails() {
    const salaryTable = document.getElementById('salary-table');

    // Clear existing table rows
    while (salaryTable.rows.length > 1) {
        salaryTable.deleteRow(1);
    }

    // Add new table rows
    salaryData.forEach((salary) => {
        const row = salaryTable.insertRow();
        row.innerHTML = `
            <td>${salary.employeeId}</td>
            <td>${salary.employeeName}</td>
            <td>${salary.basicSalary}</td>
            <td>${salary.hra}</td>
            <td>${salary.ta}</td>
            <td>${calculateTotalSalary(salary)}</td>
        `;
    });
}

// Display salary details
displaySalaryDetails();

