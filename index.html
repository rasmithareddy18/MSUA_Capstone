<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Route 39: Urban Analytics Capstone</title>
    <style>
        :root {
            --gt-gold: #B3A369;
            --gt-blue: #003057;
            --bg-dark: #1a1a1a;
        }
        body, html {
            margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f8f9fa; color: #333; scroll-behavior: smooth;
        }
        /* Hero Section */
        #hero {
            position: relative; height: 100vh; background: var(--bg-dark);
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            text-align: center; color: white; overflow: hidden;
        }
        canvas { position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 1; opacity: 0.6; }
        .hero-content { position: relative; z-index: 2; padding: 20px; }
        .hero-content h1 { font-size: 3.5rem; margin-bottom: 10px; color: var(--gt-gold); }
        .hero-content p { font-size: 1.5rem; max-width: 800px; margin: 0 auto; }
        
        /* Sticky Navigation */
        nav {
            position: sticky; top: 0; background: var(--gt-blue); padding: 15px 0;
            z-index: 100; display: flex; justify-content: center; gap: 20px;
        }
        nav a {
            color: white; text-decoration: none; font-weight: bold; padding: 8px 16px;
            border-radius: 20px; transition: background 0.3s;
        }
        nav a:hover { background: var(--gt-gold); }

        /* Content Sections */
        section { max-width: 1200px; margin: 60px auto; padding: 0 20px; }
        h2 { color: var(--gt-blue); font-size: 2.2rem; border-bottom: 2px solid var(--gt-gold); padding-bottom: 10px; }
        p { font-size: 1.1rem; line-height: 1.6; }
        
        /* Plotly iFrame Containers */
        .iframe-container {
            width: 100%; height: 650px; border: 1px solid #ddd;
            border-radius: 8px; overflow: hidden; margin-top: 20px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        iframe { width: 100%; height: 100%; border: none; }
    </style>
</head>
<body>

    <!-- Hero Section with Canvas Animation -->
    <header id="hero">
        <canvas id="abmCanvas"></canvas>
        <div class="hero-content">
            <h1>Evaluating Route 39</h1>
            <p>Quantifying the compounding impact of spatial redundancy and operational friction through Agent-Based Modeling.</p>
        </div>
    </header>

    <!-- Navigation -->
    <nav>
        <a href="#overview">Overview</a>
        <a href="#friction">Operational Friction</a>
        <a href="#equity">Demographic Equity</a>
        <a href="#simulation">Digital Twin Simulation</a>
    </nav>

    <!-- Project Overview -->
    <section id="overview">
        <h2>Project Overview</h2>
        <p>This master's capstone evaluates MARTA Route 39, shifting transit planning from theoretical scheduling to empirical, passenger-centric reality. By integrating real-time delay telemetry with ACS 2022 demographic data, this study pinpoints exactly where bus bunching and physical stop redundancy disproportionately punish transit-reliant populations.</p>
    </section>

    <!-- Operational Friction Maps -->
    <section id="friction">
        <h2>Operational Wait-Time Profiling</h2>
        <p>Standard municipal models assume buses arrive as scheduled. This framework reconstructs actual headways using GTFS telemetry to calculate the exact wait-time penalty riders experience at every node.</p>
        <div class="iframe-container">
            <!-- Ensure your Python script exported to this exact filename -->
            <iframe src="ABM_Passenger_Fallout.html"></iframe> 
        </div>
    </section>

    <!-- Digital Twin Simulation -->
    <section id="simulation">
        <h2>Agent-Based Simulation (Digital Twin)</h2>
        <p>Digital agents evaluate local wait-time penalties against demographic-driven tolerance thresholds. The baseline simulation below reveals a critical 78% abandonment rate clustered heavily along the Buford Highway corridor.</p>
        <div class="iframe-container">
            <!-- Ensure your Python script exported to this exact filename -->
            <iframe src="ABM_Animated_Simulation.html"></iframe>
        </div>
    </section>

    <!-- Simple Canvas Animation Script -->
    <script>
        const canvas = document.getElementById('abmCanvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth; canvas.height = window.innerHeight;
        
        let agents = [];
        for(let i=0; i<100; i++) {
            agents.push({
                x: Math.random() * canvas.width,
                y: Math.random() * canvas.height,
                radius: Math.random() * 3 + 1,
                vx: (Math.random() - 0.5) * 2,
                vy: (Math.random() - 0.5) * 2
            });
        }

        function animate() {
            requestAnimationFrame(animate);
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = '#B3A369';
            agents.forEach(agent => {
                agent.x += agent.vx; agent.y += agent.vy;
                if(agent.x < 0 || agent.x > canvas.width) agent.vx *= -1;
                if(agent.y < 0 || agent.y > canvas.height) agent.vy *= -1;
                ctx.beginPath();
                ctx.arc(agent.x, agent.y, agent.radius, 0, Math.PI * 2);
                ctx.fill();
            });
        }
        animate();
    </script>
</body>
</html>