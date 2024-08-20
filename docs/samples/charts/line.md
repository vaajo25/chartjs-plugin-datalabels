<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chart.js dengan Data Labels</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/chartjs-plugin-datalabels@2.0.0/dist/chartjs-plugin-datalabels.min.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .container {
            width: 80%;
            margin: 0 auto;
        }
        canvas {
            max-width: 100%;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Chart.js dengan Data Labels</h1>
        <canvas id="myChart"></canvas>
    </div>

    <script>
        // Data untuk Chart
        const data = {
            labels: ['A', 'B', 'C', 'D', 'E'],
            datasets: [{
                label: 'Nilai',
                data: [10, 20, 30, 40, 50],
                backgroundColor: 'rgba(75, 192, 192, 0.2)',
                borderColor: 'rgba(75, 192, 192, 1)',
                borderWidth: 1
            }]
        };

        // Membuat Chart
        const ctx = document.getElementById('myChart').getContext('2d');
        new Chart(ctx, {
            type: 'bar', // Jenis chart
            data: data,
            options: {
                plugins: {
                    datalabels: {
                        display: true, // Menampilkan label data
                        align: 'end', // Posisi label data
                        anchor: 'end', // Tempat label data
                        formatter: (value) => `${value}`, // Format label data
                        color: '#000', // Warna label data
                        font: {
                            weight: 'bold' // Ketebalan font
                        }
                    }
                },
                scales: {
                    x: {
                        beginAtZero: true
                    }
                }
            }
        });
    </script>
</body>
</html>
