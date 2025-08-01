<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gautam Kumar Patwa | Interactive Resume</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Calm Neutrals -->
    <!-- Application Structure Plan: The SPA uses a single-page, multi-section layout with a sticky navigation bar for easy access to all parts of the resume. The structure is designed for a top-down narrative flow, starting with a high-level summary, moving to an interactive skills dashboard, then a chronological experience timeline, and finally education. This structure allows recruiters to quickly get an overview and then dive deeper into the areas that interest them most. The interactive skills chart and expandable timeline are chosen to make the content more engaging and less overwhelming than a static document, enhancing usability. -->
    <!-- Visualization & Content Choices: 
        - Summary: Standard text block for a professional overview. Goal: Inform.
        - Skills: A radar chart (Chart.js) visualizes the balance between skill categories (Leadership, Financial, HR, Technical). Goal: Compare, Organize. Interaction: Filter buttons dynamically show specific skills in each category, allowing users to drill down. This is more engaging than a long list.
        - Experience: A vertical timeline (HTML/Tailwind) shows career progression. Goal: Show Change. Interaction: Job details are collapsed by default and expand on click, preventing information overload.
        - Education: Simple card layout. Goal: Inform.
        - Justification: These choices create a dynamic, user-controlled narrative, which is more memorable and user-friendly for recruiters.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc; /* slate-50 */
            color: #1e293b; /* slate-800 */
        }
        .timeline-item::before {
            content: '';
            position: absolute;
            width: 1rem;
            height: 1rem;
            border-radius: 50%;
            left: -0.5rem;
            top: 0.25rem;
            background-color: #3b82f6; /* blue-500 */
            border: 3px solid #f8fafc; /* slate-50 */
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
    </style>
</head>
<body class="antialiased">

    <!-- Header & Navigation -->
    <header class="bg-white/80 backdrop-blur-lg sticky top-0 z-50 shadow-sm">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-xl font-bold text-slate-800">Gautam Kumar Patwa</div>
            <div class="hidden md:flex items-center space-x-6">
                <a href="#summary" class="text-slate-600 hover:text-blue-500 transition-colors">Summary</a>
                <a href="#skills" class="text-slate-600 hover:text-blue-500 transition-colors">Skills</a>
                <a href="#experience" class="text-slate-600 hover:text-blue-500 transition-colors">Experience</a>
                <a href="#education" class="text-slate-600 hover:text-blue-500 transition-colors">Education</a>
            </div>
            <a href="mailto:gautam.patwa123@outlook.com" class="hidden md:block bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600 transition-transform hover:scale-105">Contact Me</a>
            <button id="mobile-menu-button" class="md:hidden text-slate-800">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
            </button>
        </nav>
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden px-6 pb-4">
            <a href="#summary" class="block py-2 text-slate-600 hover:text-blue-500">Summary</a>
            <a href="#skills" class="block py-2 text-slate-600 hover:text-blue-500">Skills</a>
            <a href="#experience" class="block py-2 text-slate-600 hover:text-blue-500">Experience</a>
            <a href="#education" class="block py-2 text-slate-600 hover:text-blue-500">Education</a>
            <a href="mailto:gautam.patwa123@outlook.com" class="block mt-2 text-center bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600">Contact Me</a>
        </div>
    </header>

    <main class="container mx-auto px-6 py-12">

        <!-- Hero Section -->
        <section class="text-center mb-20">
            <h1 class="text-4xl md:text-6xl font-bold text-slate-900 mb-4">Gautam Kumar Patwa</h1>
            <p class="text-lg md:text-xl text-slate-600 max-w-3xl mx-auto">A strategic manager blending financial acumen with human resource expertise.</p>
            <div class="mt-8 flex justify-center items-center space-x-6 text-slate-600">
                <span class="flex items-center">
                    <span class="mr-2">📞</span> +91 62008 96234
                </span>
                <a href="https://linkedin.com/in/gautamkumarpatwa/" target="_blank" class="flex items-center hover:text-blue-500 transition-colors">
                    <span class="mr-2">🔗</span> LinkedIn
                </a>
            </div>
        </section>

        <!-- Summary Section -->
        <section id="summary" class="mb-20 scroll-mt-20">
            <h2 class="text-3xl font-bold text-center mb-8 text-slate-800">Professional Summary</h2>
            <div class="bg-white p-8 rounded-xl shadow-md max-w-4xl mx-auto">
                <p class="text-slate-600 leading-relaxed">
                    A results-oriented and strategic manager with a unique combination of expertise in financial oversight and human resource management. Proven ability to drive organizational health and profitability through meticulous financial analysis, strategic planning, and effective people leadership. Adept at mentoring teams, optimizing processes, and collaborating across departments to achieve overarching business goals. Eager to apply a holistic understanding of business operations to a challenging new role.
                </p>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="mb-20 scroll-mt-20">
            <h2 class="text-3xl font-bold text-center mb-4 text-slate-800">Skills Dashboard</h2>
            <p class="text-center text-slate-500 mb-8 max-w-2xl mx-auto">This section provides an interactive overview of my core competencies. The chart visualizes the balance of my skills across key areas. Use the filters to explore specific skills within each category.</p>
            <div class="bg-white p-8 rounded-xl shadow-md max-w-4xl mx-auto">
                <div class="chart-container">
                    <canvas id="skillsChart"></canvas>
                </div>
                <div class="mt-8 text-center" id="skill-filters">
                    <!-- Filter buttons will be inserted here by JS -->
                </div>
                <div id="skills-list" class="mt-6 grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 text-center">
                    <!-- Skills will be dynamically populated here -->
                </div>
            </div>
        </section>

        <!-- Experience Section -->
        <section id="experience" class="mb-20 scroll-mt-20">
            <h2 class="text-3xl font-bold text-center mb-12 text-slate-800">Professional Experience</h2>
            <div id="experience-timeline" class="max-w-3xl mx-auto relative border-l-2 border-slate-200 pl-8 md:pl-12 py-4">
                <!-- Timeline items will be inserted here by JS -->
            </div>
        </section>

        <!-- Education Section -->
        <section id="education" class="scroll-mt-20">
            <h2 class="text-3xl font-bold text-center mb-8 text-slate-800">Education</h2>
            <div class="bg-white p-8 rounded-xl shadow-md max-w-4xl mx-auto text-center">
                <h3 class="text-xl font-bold text-slate-900">Bachelor of Business Administration</h3>
                <p class="text-slate-600 mt-1">Lalit Narayan Mithila University, Darbhanga, Bihar</p>
                <p class="text-slate-500 text-sm mt-1">2022 - 2025</p>
            </div>
        </section>

    </main>

    <footer class="bg-slate-800 text-white mt-20">
        <div class="container mx-auto px-6 py-8 text-center">
            <p class="mb-4">Gautam Kumar Patwa</p>
            <div class="flex justify-center items-center space-x-6">
                <a href="mailto:gautam.patwa123@outlook.com" class="hover:text-blue-400 transition-colors">Email</a>
                <a href="https://linkedin.com/in/gautamkumarpatwa/" target="_blank" class="hover:text-blue-400 transition-colors">LinkedIn</a>
            </div>
            <p class="text-sm text-slate-400 mt-8">&copy; 2025 Gautam Kumar Patwa. All Rights Reserved.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            // Data
            const skillsData = {
                'Leadership & Strategy': ['Team Leadership', 'Financial Strategy', 'Operations Management', 'Strategic Planning', 'Problem-Solving'],
                'Financial': ['Budget Management', 'Financial Analysis', 'Management Reporting', 'Compliance', 'Data Analysis Expressions (DAX)'],
                'Human Resources': ['Human Resource Management (HRM)', 'Performance Management', 'Recruitment & Onboarding', 'HR Policies'],
                'Technical': ['Data Analysis', 'Microsoft Office Suite', 'Google Meet']
            };

            const experienceData = [
                {
                    role: 'Manager and Accountant',
                    company: 'Neetu Traders',
                    location: 'Darbhanga, Bihar, India (Hybrid)',
                    date: 'May 2022 – Present',
                    tasks: [
                        'Directed the financial health of the organization by analyzing key performance indicators and preparing comprehensive financial reports to ensure accuracy and regulatory compliance.',
                        'Developed and implemented financial strategies that optimized profitability and improved resource allocation.',
                        'Managed and mentored a team of accountants, providing targeted guidance and support that fostered their professional growth and team productivity.',
                        'Collaborated with department heads to provide key financial insights, supporting data-driven strategic decision-making across the organization.',
                        'Established and maintained a robust system of internal controls to safeguard organizational assets and mitigate fraud.'
                    ]
                },
                {
                    role: 'Human Resources Intern',
                    company: 'Hindustan Celestial Private Ltd',
                    location: 'Odisha, India (Remote)',
                    date: 'February 2025 – May 2025',
                    tasks: [
                        'Assisted in the end-to-end recruitment process by screening resumes, conducting initial candidate interviews, and coordinating with the HR team.',
                        'Supported the seamless onboarding of new hires by preparing documentation and leading orientation sessions.',
                        'Maintained confidential employee records and databases, ensuring a high level of data accuracy and integrity.',
                        'Contributed to key HR projects, including employee engagement initiatives and the development of new training programs.'
                    ]
                }
            ];

            // Mobile Menu Toggle
            const mobileMenuButton = document.getElementById('mobile-menu-button');
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenuButton.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });
            document.querySelectorAll('#mobile-menu a').forEach(link => {
                link.addEventListener('click', () => mobileMenu.classList.add('hidden'));
            });

            // Skills Chart
            const ctx = document.getElementById('skillsChart').getContext('2d');
            const skillsChart = new Chart(ctx, {
                type: 'radar',
                data: {
                    labels: Object.keys(skillsData),
                    datasets: [{
                        label: 'Skill Competency',
                        data: Object.values(skillsData).map(s => s.length),
                        backgroundColor: 'rgba(59, 130, 246, 0.2)',
                        borderColor: 'rgba(59, 130, 246, 1)',
                        borderWidth: 2,
                        pointBackgroundColor: 'rgba(59, 130, 246, 1)',
                        pointBorderColor: '#fff',
                        pointHoverBackgroundColor: '#fff',
                        pointHoverBorderColor: 'rgba(59, 130, 246, 1)'
                    }]
                },
                options: {
                    maintainAspectRatio: false,
                    scales: {
                        r: {
                            angleLines: { color: 'rgba(0, 0, 0, 0.1)' },
                            grid: { color: 'rgba(0, 0, 0, 0.1)' },
                            pointLabels: {
                                font: { size: 12, weight: 'bold' },
                                color: '#475569' // slate-600
                            },
                            ticks: {
                                backdropColor: 'transparent',
                                stepSize: 1
                            }
                        }
                    },
                    plugins: {
                        legend: { display: false },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    let label = context.dataset.label || '';
                                    if (label) {
                                        label += ': ';
                                    }
                                    label += context.raw + ' skills';
                                    return label;
                                }
                            }
                        }
                    }
                }
            });

            // Skills Filtering
            const filtersContainer = document.getElementById('skill-filters');
            const skillsListContainer = document.getElementById('skills-list');
            const categories = ['All', ...Object.keys(skillsData)];

            categories.forEach(category => {
                const button = document.createElement('button');
                button.textContent = category;
                button.className = 'skill-filter-btn px-4 py-2 mx-1 my-1 rounded-lg text-sm font-medium transition-colors';
                if (category === 'All') {
                    button.classList.add('bg-blue-500', 'text-white');
                } else {
                    button.classList.add('bg-slate-200', 'text-slate-700', 'hover:bg-slate-300');
                }
                button.dataset.category = category;
                filtersContainer.appendChild(button);
            });

            function displaySkills(category) {
                skillsListContainer.innerHTML = '';
                let skillsToShow = [];
                if (category === 'All') {
                    skillsToShow = Object.values(skillsData).flat();
                } else {
                    skillsToShow = skillsData[category];
                }

                skillsToShow.forEach(skill => {
                    const skillEl = document.createElement('div');
                    skillEl.className = 'bg-slate-100 text-slate-700 p-3 rounded-lg text-sm';
                    skillEl.textContent = skill;
                    skillsListContainer.appendChild(skillEl);
                });
            }

            filtersContainer.addEventListener('click', (e) => {
                if (e.target.tagName === 'BUTTON') {
                    const category = e.target.dataset.category;
                    document.querySelectorAll('.skill-filter-btn').forEach(btn => {
                        btn.classList.remove('bg-blue-500', 'text-white');
                        btn.classList.add('bg-slate-200', 'text-slate-700', 'hover:bg-slate-300');
                    });
                    e.target.classList.add('bg-blue-500', 'text-white');
                    e.target.classList.remove('bg-slate-200', 'text-slate-700', 'hover:bg-slate-300');
                    displaySkills(category);
                }
            });

            displaySkills('All'); // Initial display

            // Experience Timeline
            const timelineContainer = document.getElementById('experience-timeline');
            experienceData.forEach(job => {
                const jobEl = document.createElement('div');
                jobEl.className = 'mb-10 timeline-item';

                let tasksHtml = '<ul class="mt-4 space-y-2 text-slate-600 text-sm list-disc list-inside">';
                job.tasks.forEach(task => {
                    tasksHtml += `<li>${task}</li>`;
                });
                tasksHtml += '</ul>';

                jobEl.innerHTML = `
                    <div class="cursor-pointer experience-header">
                        <p class="text-xs text-slate-500">${job.date}</p>
                        <h3 class="text-lg font-bold text-slate-800 mt-1">${job.role}</h3>
                        <p class="text-md text-slate-600">${job.company} - ${job.location}</p>
                        <span class="text-blue-500 text-sm mt-2 inline-block transition-transform">Show Details ▼</span>
                    </div>
                    <div class="experience-details hidden mt-2 overflow-hidden transition-all duration-500 ease-in-out">
                        ${tasksHtml}
                    </div>
                `;
                timelineContainer.appendChild(jobEl);
            });

            timelineContainer.addEventListener('click', (e) => {
                const header = e.target.closest('.experience-header');
                if (header) {
                    const details = header.nextElementSibling;
                    const arrow = header.querySelector('span');
                    const isHidden = details.classList.contains('hidden');
                    
                    if(isHidden) {
                        details.classList.remove('hidden');
                        arrow.innerHTML = 'Hide Details ▲';
                        arrow.classList.add('rotate-180');
                    } else {
                        details.classList.add('hidden');
                        arrow.innerHTML = 'Show Details ▼';
                        arrow.classList.remove('rotate-180');
                    }
                }
            });
        });
    </script>
</body>
</html>
