<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Me - Rohit Kumar Senapati</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .background-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .floating-shapes {
            position: absolute;
            width: 100px;
            height: 100px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        .shape1 { top: 20%; left: 10%; animation-delay: 0s; }
        .shape2 { top: 60%; left: 80%; animation-delay: 2s; transform: scale(0.7); }
        .shape3 { top: 80%; left: 20%; animation-delay: 4s; transform: scale(1.2); }
        .shape4 { top: 30%; left: 70%; animation-delay: 1s; transform: scale(0.5); }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .card {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            border-radius: 24px;
            padding: 50px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
            transition: transform 0.3s ease;
        }

        .card:hover {
            transform: translateY(-10px);
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4, #feca57);
            animation: rainbow 3s linear infinite;
        }

        @keyframes rainbow {
            0% { background-position: 0% 50%; }
            100% { background-position: 100% 50%; }
        }

        .profile-section {
            text-align: center;
            margin-bottom: 40px;
        }

        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 48px;
            color: white;
            font-weight: bold;
            animation: pulse 2s infinite;
            border: 4px solid rgba(255, 255, 255, 0.3);
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        h1 {
            font-size: 2.5rem;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .subtitle {
            color: #666;
            font-size: 1.2rem;
            margin-bottom: 30px;
            font-weight: 300;
        }

        .tech-stack {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
            flex-wrap: wrap;
        }

        .tech-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 16px;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 2px solid transparent;
        }

        .tech-item:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 1);
            border-color: #667eea;
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.2);
        }

        .tech-icon {
            width: 50px;
            height: 50px;
            margin-bottom: 10px;
            transition: transform 0.3s ease;
        }

        .tech-item:hover .tech-icon {
            transform: scale(1.2) rotate(5deg);
        }

        .tech-name {
            font-size: 0.9rem;
            font-weight: 600;
            color: #333;
        }

        .bio {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            padding: 30px;
            border-radius: 20px;
            margin: 30px 0;
            border-left: 4px solid #667eea;
        }

        .bio p {
            color: #555;
            line-height: 1.8;
            font-size: 1.1rem;
            margin: 0;
        }

        .interests {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .interest-card {
            background: rgba(255, 255, 255, 0.6);
            padding: 25px;
            border-radius: 16px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .interest-card:hover {
            background: rgba(255, 255, 255, 0.9);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }

        .interest-icon {
            font-size: 2rem;
            margin-bottom: 15px;
            display: block;
        }

        .interest-title {
            font-weight: 600;
            color: #333;
            margin-bottom: 8px;
        }

        .interest-desc {
            font-size: 0.9rem;
            color: #666;
        }

        .contact-section {
            text-align: center;
            margin-top: 40px;
            padding-top: 30px;
            border-top: 1px solid rgba(102, 126, 234, 0.2);
        }

        .contact-btn {
            display: inline-block;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            margin: 10px;
            box-shadow: 0 8px 20px rgba(102, 126, 234, 0.3);
        }

        .contact-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 30px rgba(102, 126, 234, 0.4);
        }

        @media (max-width: 768px) {
            .container {
                padding: 20px 10px;
            }
            
            .card {
                padding: 30px 25px;
                margin: 20px 10px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .tech-stack {
                gap: 15px;
            }
            
            .tech-item {
                padding: 15px;
            }
        }

        .typing-animation {
            border-right: 2px solid #667eea;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            50% { border-color: transparent; }
        }
    </style>
</head>
<body>
    <div class="background-animation">
        <div class="floating-shapes shape1"></div>
        <div class="floating-shapes shape2"></div>
        <div class="floating-shapes shape3"></div>
        <div class="floating-shapes shape4"></div>
    </div>

    <div class="container">
        <div class="card">
            <div class="profile-section">
                <div class="profile-img">RK</div>
                <h1>Rohit Kumar Senapati</h1>
                <div class="subtitle typing-animation">Future Data Scientist & Tech Enthusiast</div>
            </div>

            <div class="tech-stack">
                <div class="tech-item">
                    <svg class="tech-icon" viewBox="0 0 128 128">
                        <linearGradient id="python-original-a" gradientUnits="userSpaceOnUse" x1="70.252" y1="1237.476" x2="170.659" y2="1151.089" gradientTransform="matrix(.563 0 0 -.568 -29.215 707.817)">
                            <stop offset="0" stop-color="#5A9FD4"/>
                            <stop offset="1" stop-color="#306998"/>
                        </linearGradient>
                        <linearGradient id="python-original-b" gradientUnits="userSpaceOnUse" x1="209.474" y1="1098.811" x2="173.62" y2="1149.537" gradientTransform="matrix(.563 0 0 -.568 -29.215 707.817)">
                            <stop offset="0" stop-color="#FFD43B"/>
                            <stop offset="1" stop-color="#FFE873"/>
                        </linearGradient>
                        <path fill="url(#python-original-a)" d="M63.391 1.988c-4.222.02-8.252.379-11.8 1.007-10.45 1.846-12.346 5.71-12.346 12.837v9.411h24.693v3.137H29.977c-7.176 0-13.46 4.313-15.426 12.521-2.268 9.405-2.368 15.275 0 25.096 1.755 7.311 5.947 12.519 13.124 12.519h8.491V67.234c0-8.151 7.051-15.34 15.426-15.34h24.665c6.866 0 12.346-5.654 12.346-12.548V15.833c0-6.693-5.646-11.72-12.346-12.837-4.244-.706-8.645-1.027-12.866-1.008zM50.037 9.557c2.55 0 4.634 2.117 4.634 4.721 0 2.593-2.083 4.69-4.634 4.69-2.56 0-4.633-2.097-4.633-4.69-.001-2.604 2.073-4.721 4.633-4.721z" transform="translate(0 10.26)"/>
                        <path fill="url(#python-original-b)" d="M91.682 28.38v10.966c0 8.5-7.208 15.655-15.426 15.655H51.591c-6.756 0-12.346 5.783-12.346 12.549v23.515c0 6.691 5.818 10.628 12.346 12.547 7.816 2.297 15.312 2.713 24.665 0 6.216-1.801 12.346-5.423 12.346-12.547v-9.412H63.938v-3.138h37.012c7.176 0 9.852-5.005 12.348-12.519 2.578-7.735 2.467-15.174 0-25.096-1.774-7.145-5.161-12.521-12.348-12.521H91.682zm-13.634 64.17c2.561 0 4.634 2.097 4.634 4.692 0 2.602-2.074 4.719-4.634 4.719-2.55 0-4.633-2.117-4.633-4.719 0-2.595 2.083-4.692 4.633-4.692z" transform="translate(0 10.26)"/>
                    </svg>
                    <span class="tech-name">Python</span>
                </div>
                <div class="tech-item">
                    <svg class="tech-icon" viewBox="0 0 128 128">
                        <defs>
                            <linearGradient id="r-original-a" gradientUnits="userSpaceOnUse" x1="24.527" y1="105.613" x2="24.527" y2="31.338">
                                <stop offset="0" stop-color="#CBCED0"/>
                                <stop offset="1" stop-color="#84838B"/>
                            </linearGradient>
                            <linearGradient id="r-original-b" gradientUnits="userSpaceOnUse" x1="50.27" y1="105.613" x2="50.27" y2="31.338">
                                <stop offset="0" stop-color="#276DC3"/>
                                <stop offset="1" stop-color="#165CAA"/>
                            </linearGradient>
                        </defs>
                        <circle cx="64" cy="64" r="50" fill="url(#r-original-b)"/>
                        <path fill="url(#r-original-a)" d="M48.854 31.338c-7.987 0-14.473 6.487-14.473 14.473v4.614c0 1.681 1.363 3.044 3.044 3.044s3.044-1.363 3.044-3.044v-4.614c0-4.625 3.759-8.385 8.385-8.385h6.088c1.681 0 3.044-1.363 3.044-3.044s-1.363-3.044-3.044-3.044h-6.088z"/>
                        <text x="64" y="70" text-anchor="middle" font-family="Arial, sans-serif" font-size="28" font-weight="bold" fill="white">R</text>
                    </svg>
                    <span class="tech-name">R</span>
                </div>
                <div class="tech-item">
                    <svg class="tech-icon" viewBox="0 0 128 128">
                        <g fill="#181616">
                            <path fill-rule="evenodd" clip-rule="evenodd" d="M64 5.103c-33.347 0-60.388 27.035-60.388 60.388 0 26.682 17.303 49.317 41.297 57.303 3.017.56 4.125-1.31 4.125-2.905 0-1.44-.056-6.197-.082-11.243-16.8 3.653-20.345-7.125-20.345-7.125-2.747-6.98-6.705-8.836-6.705-8.836-5.48-3.748.413-3.67.413-3.67 6.063.425 9.257 6.223 9.257 6.223 5.386 9.23 14.127 6.562 17.573 5.02.542-3.903 2.107-6.568 3.834-8.076-13.413-1.525-27.514-6.704-27.514-29.843 0-6.593 2.36-11.98 6.223-16.21-.628-1.52-2.695-7.662.584-15.980 0 0 5.07-1.623 16.61 6.19C53.7 35 58.867 34.327 64 34.304c5.13.023 10.3.694 15.127 2.033 11.526-7.813 16.59-6.19 16.59-6.19 3.287 8.317 1.22 14.46.593 15.98 3.872 4.23 6.215 9.617 6.215 16.21 0 23.194-14.127 28.3-27.574 29.796 2.167 1.874 4.097 5.55 4.097 11.183 0 8.08-.07 14.583-.07 16.572 0 1.607 1.088 3.49 4.148 2.897 23.98-7.994 41.263-30.622 41.263-57.294C124.388 32.14 97.35 5.104 64 5.104z"/>
                            <path d="M26.484 91.806c-.133.3-.605.39-1.035.185-.44-.196-.685-.605-.543-.906.13-.31.603-.395 1.04-.188.44.197.69.61.537.91zm2.446 2.729c-.287.267-.85.143-1.232-.28-.396-.42-.47-.983-.177-1.254.298-.266.844-.14 1.24.28.394.426.472.984.17 1.255zM31.312 98.012c-.37.258-.976.017-1.35-.52-.37-.538-.37-1.183.01-1.44.373-.258.97-.025 1.35.507.368.545.368 1.19-.01 1.452zm3.261 3.361c-.33.365-1.036.267-1.552-.23-.527-.487-.674-1.18-.343-1.544.336-.366 1.045-.264 1.564.23.527.486.686 1.18.333 1.543zm4.5 1.951c-.147.473-.825.688-1.51.486-.683-.207-1.13-.76-.99-1.238.14-.477.823-.7 1.512-.485.683.206 1.13.756.988 1.237zm4.943.361c.017.498-.563.91-1.28.92-.723.017-1.308-.387-1.315-.877 0-.503.568-.91 1.29-.924.717-.013 1.306.387 1.306.88zm4.598-.782c.086.485-.413.984-1.126 1.117-.7.13-1.35-.172-1.44-.653-.086-.498.422-.997 1.122-1.126.714-.123 1.354.17 1.444.663zm0 0"/>
                        </g>
                    </svg>
                    <span class="tech-name">GitHub</span>
                </div>
                <div class="tech-item">
                    <svg class="tech-icon" viewBox="0 0 128 128">
                        <path d="M64 7C31.1 7 4.6 30.5 4.6 60.4 4.6 85.4 21.1 106.5 43.7 114.1c1.7.3 2.3-.7 2.3-1.6 0-.8 0-2.9 0-5.7-16.5 3.6-20-7.9-20-7.9-1.5-3.8-3.7-4.8-3.7-4.8-3-.2.2-.2.2-.2 3.3.2 5.1 3.4 5.1 3.4 3 5.1 7.9 3.6 9.8 2.8.3-2.2 1.2-3.6 2.2-4.4-7.5-.9-15.4-3.8-15.4-16.6 0-3.7 1.3-6.7 3.5-9.1-.4-0.9-1.5-4.3.3-8.9 0 0 2.8-.9 9.2 3.5 2.7-.8 5.5-1.2 8.3-1.2s5.6.4 8.3 1.2c6.4-4.4 9.2-3.5 9.2-3.5 1.8 4.6.7 8 .3 8.9 2.2 2.4 3.5 5.4 3.5 9.1 0 12.8-7.9 15.7-15.4 16.6 1.2 1 2.3 3.1 2.3 6.2 0 4.5 0 8.1 0 9.2 0 .9.6 1.9 2.3 1.6C106.9 106.5 123.4 85.4 123.4 60.4 123.4 30.5 96.9 7 64 7z" fill="#F77F00"/>
                        <path d="M64 0C28.7 0 0 28.7 0 64s28.7 64 64 64 64-28.7 64-64S99.3 0 64 0zM25.5 96.1C23.9 98.3 21.3 100 18.1 100c-1.2 0-2.4-.2-3.5-.7-2.2-.9-3.8-2.9-4.4-5.4-.6-2.5 0-5.1 1.6-7.1 2.8-3.5 7.9-4.1 11.4-1.3 3.5 2.8 4.1 7.9 1.3 11.4z" fill="#333"/>
                    </svg>
                    <span class="tech-name">Linux</span>
                </div>
            </div>

            <div class="bio">
                <p>
                    Hello! I'm Rohit Kumar Senapati, a passionate Computer Science student with a deep fascination for Data Science. 
                    Currently pursuing my B-Tech degree, I'm on an exciting journey to transform raw data into meaningful insights. 
                    I believe in the power of technology to solve real-world problems and am constantly exploring new ways to apply 
                    machine learning and statistical analysis to create impactful solutions.
                </p>
            </div>

            <div class="interests">
                <div class="interest-card">
                    <span class="interest-icon">📊</span>
                    <div class="interest-title">Data Analytics</div>
                    <div class="interest-desc">Turning complex datasets into actionable insights</div>
                </div>
                <div class="interest-card">
                    <span class="interest-icon">🤖</span>
                    <div class="interest-title">Machine Learning</div>
                    <div class="interest-desc">Building intelligent systems that learn and adapt</div>
                </div>
                <div class="interest-card">
                    <span class="interest-icon">📈</span>
                    <div class="interest-title">Statistical Modeling</div>
                    <div class="interest-desc">Creating predictive models for better decisions</div>
                </div>
                <div class="interest-card">
                    <span class="interest-icon">💻</span>
                    <div class="interest-title">Programming</div>
                    <div class="interest-desc">Crafting elegant code solutions</div>
                </div>
            </div>

            <div class="contact-section">
                <h3 style="margin-bottom: 20px; color: #333;">Let's Connect!</h3>
                <a href="#" class="contact-btn">Portfolio</a>
                <a href="#" class="contact-btn">LinkedIn</a>
                <a href="#" class="contact-btn">GitHub</a>
            </div>
        </div>
    </div>

    <script>
        // Add some interactive animations
        document.addEventListener('DOMContentLoaded', function() {
            // Typing animation for subtitle
            const subtitle = document.querySelector('.subtitle');
            const text = 'Future Data Scientist & Tech Enthusiast';
            subtitle.textContent = '';
            
            let i = 0;
            function typeWriter() {
                if (i < text.length) {
                    subtitle.textContent += text.charAt(i);
                    i++;
                    setTimeout(typeWriter, 100);
                }
            }
            
            setTimeout(typeWriter, 1000);

            // Add hover effects to tech items
            const techItems = document.querySelectorAll('.tech-item');
            techItems.forEach(item => {
                item.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-8px) scale(1.05)';
                });
                
                item.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                });
            });

            // Parallax effect for floating shapes
            document.addEventListener('mousemove', function(e) {
                const shapes = document.querySelectorAll('.floating-shapes');
                const x = e.clientX / window.innerWidth;
                const y = e.clientY / window.innerHeight;
                
                shapes.forEach((shape, index) => {
                    const speed = (index + 1) * 0.5;
                    shape.style.transform += ` translate(${x * speed}px, ${y * speed}px)`;
                });
            });
        });
    </script>
</body>
</html>
