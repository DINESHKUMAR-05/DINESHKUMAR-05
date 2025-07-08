<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dineshkumar S - Profile & Skills</title>
    <!-- Chosen Palette: Energetic & Playful -->
    <!-- Application Structure Plan: A focused single-page layout presenting only the core profile summary and technical skills. This streamlined structure is ideal for quick overviews, allowing users to immediately grasp the candidate's professional identity and technical capabilities without additional context. The skills are visualized using a horizontal bar chart for clear comparison. -->
    <!-- Visualization & Content Choices: 
        - Profile Summary -> Goal: Inform -> Viz: Text Block (HTML/CSS) -> Interaction: None -> Justification: Provides a concise introduction to the candidate.
        - Skills Overview -> Goal: Compare -> Viz: Horizontal Bar Chart (Chart.js/Canvas) -> Interaction: Hover for details -> Justification: A bar chart effectively compares proficiency across different skills, offering a quick, comparative overview of technical strengths.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px; /* Increased max-width for better chart readability */
            height: 350px; /* Adjusted height for better chart display */
            margin: 0 auto;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
    </style>
</head>
<body class="bg-[#FDF0D5]">

    <div class="container mx-auto p-6 md:p-12">
        <!-- Header / Profile Section -->
        <header class="text-center mb-16">
            <h1 class="text-5xl md:text-7xl font-black text-[#003049]">DINESHKUMAR S</h1>
            <p class="text-xl md:text-2xl text-[#C1121F] font-semibold mt-2">Machine Learning & Data Science</p>
            <p class="text-lg md:text-xl text-gray-700 max-w-3xl mx-auto mt-6">
                Passionate machine learning scholar, seeking challenging roles to fully leverage and expand my skills, with a commitment to continuous learning at every opportunity.
            </p>
            <div class="flex justify-center items-center space-x-4 text-sm text-gray-600 mt-4">
                <span>dineshkumar.s51202@gmail.com</span>
                <span>•</span>
                <span>Coimbatore, India</span>
                <span>•</span>
                <span>+91 9585534869</span>
            </div>
        </header>

        <!-- Skills -->
        <section class="mb-20">
            <h2 class="text-4xl font-bold text-center text-[#003049] mb-10">Core Skills</h2>
            <div class="bg-white p-8 rounded-2xl shadow-lg">
                <p class="text-center text-gray-700 max-w-2xl mx-auto mb-8">This section provides a summary of my technical toolkit. It covers the programming languages, databases, machine learning frameworks, and cloud platforms I'm proficient with. These are the core technologies I use to build and deploy effective AI solutions.</p>
                <div class="chart-container">
                    <canvas id="skillsChart"></canvas>
                </div>
            </div>
        </section>

    </div>

    <script>
        // Skills Chart
        const skillsCtx = document.getElementById('skillsChart').getContext('2d');
        new Chart(skillsCtx, {
            type: 'bar',
            data: {
                labels: ['Python', 'Tensorflow', 'Pytorch', 'LangChain', 'CrewAI', 'Scikit Learn', 'AWS'],
                datasets: [{
                    label: 'Proficiency',
                    data: [95, 90, 88, 85, 85, 92, 80],
                    backgroundColor: ['#003049', '#D62828', '#F77F00', '#C1121F', '#780000', '#FCBF49', '#EAE2B7'],
                    borderColor: '#FFFFFF',
                    borderWidth: 2,
                    borderRadius: 8
                }]
            },
            options: {
                indexAxis: 'y',
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { display: false },
                    tooltip: {
                        callbacks: {
                            title: function(tooltipItems) {
                                return tooltipItems[0].label;
                            }
                        }
                    }
                },
                scales: {
                    x: {
                        grid: { display: false },
                        ticks: { display: false },
                        max: 100 // Ensure scale goes up to 100 for proficiency
                    },
                    y: {
                        grid: { display: false },
                        ticks: {
                            color: '#003049',
                            font: {
                                size: 14,
                                weight: '600'
                            }
                        }
                    }
                }
            }
        });
    </script>

</body>
</html>
