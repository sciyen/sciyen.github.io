---
layout: default
---

<!-- Website Maintaining, please see [About](./about.md) -->

<h1>朱雁丞 Yen-Cheng Chu</h1>
<div class="intro-block">
    <div>
    <!-- 我熱衷於結合科技與生活，製作 side project 或是 hacking 自己的生活。讓不會動的東西動起來是興趣，動得漂亮是浪漫。研究領域包含控制系統、非線性系統。偶爾嵌入式系統，設計電路板，或是寫網頁。 -->
    I am passionate about intergrating technology into life, making side projects, or hacking my own life. Making things that don't move come to life is interesting, and making them move beautifully is romantic. My research areas include control systems and nonlinear systems. Occasionally, I work on embedded systems, design circuit boards, or write web pages.
    </div>
    <div>
        <img src="../assets/me.jpg" class="img-circle">
    </div>
    <div>
        <ul>
            <li>Facebook: {% include icon-fb.html username=site.facebook_username url=site.facebook_url%}</li>
            {% if site.linkedin_username %}
            <li>LinkedIn: {% include icon-linkedin.html username=site.linkedin_username url=site.linkedin_url%}</li>
            {% endif %}
            {% if site.github_username %}
            <li>Github: {% include icon-github.html username="sciyen" %}</li>
            {% endif %}
            <li>Email: <a href="mailto:{{ site.email }}">{{ site.email }}</a></li>
        </ul>
    </div>
</div>

<h2>Skills</h2>
<div>
    <ul class="regular">
        <li>Experiences in Hybrid simulations (MATLAB Simulink)</li>
        <li>PX4 on Nuttx RTOS system (6-DoF controller and control allocation)</li>
        <li>Software-in-the-loop simulations (based on Gazebo)</li>
        <li>Flight Data Analysis (Rviz, ulog, rosbag)</li>
        <li>MCU development for 10 years (Atmega, STM32, ESP32, etc.)</li>
        <li>ROS1 Noetic and ROS2 Humble</li>
        <li>Being familier with version control software (Git)</li>
        <li>PCB layout</li>
    </ul>
</div>
<div class="skill-container">
    {% for skill in site.data.skills %}
    <ul class="score-bar">
        <h3>{{ skill.name }}</h3>
        {% for item in skill.details %}
            <li>
                <div>
                    <span>{{ item.name }}</span>
                    <p style="width: {{ item.rate }}%"></p>
                </div>
                {% if item.data %}
                <div>
                <ul>
                    {% for d in item.data %}
                    <li>{{ d }}</li>
                    {% endfor %}
                </ul>
                </div>
                {% endif %}
            </li>
        {% endfor %}
    </ul>
    {% endfor %}
</div>

<h2>Research Interests</h2>
<div>
Keywords: Robotics, Unmanned Aerial Vehicles, Control Systems, Guidance navigation and control (GNC).
</div>
<div>
<ul class="regular">
    <li>Vehicle dynamics on SE(3), including modeling and 6-DoF controls.</li>
    <li>Designing controller for under-actuated / over-actuated system</li>
    <li>control allocation algorithm development</li>
</ul>
</div>

<h3>Master's Degree Research</h3>
<p>Title: An Over-Actuated Thrust-Vectoring Modular Drone based on Cascaded Full-Pose Tracking Control with Redistributed Control Allocation for Safe Aerial Delivery Applications</p>
<div class="project-block">
    <div>
        <img src="../assets/tvmd.png">
    </div>
    <div>
        <ul class="regular">
        <li>Advisor: <a href="https://homepage.ntu.edu.tw/~fengli/">Prof. Feng-Li Lian</a></li>
        <li>Lab: <a href="https://homepage.ntu.edu.tw/~ncslab/">Networked Control Systems Laboratory (NCSLab)</a></li>
        <li>Full article is available at: <a href="http://tdr.lib.ntu.edu.tw/jspui/handle/123456789/92117">NTU Thesis and Dissertion Repository</a></li>
        </ul>
    </div>
</div>

<h4>Abstract</h4>
<div>
In this research, a Thrust-Vectoring Modular Drone (TVMD) with coaxial rotors is proposed to address delivery challenges, such as the last-mile delivery for e-commerce services and transporting time-sensitive packages to outlying islands and mountain areas, especially when natural disasters or accidents occur. The TVMD is designed with high redundancy, controllability, and reconfigurability to ensure safety, flight efficiency, mobility, and maneuverability. The modular design of the drone enables optimal task performance by changing the type and number of agents.
</div>

<h2>Educations</h2>
<ul class="timeline">
{% for item in site.data.educations %}
    <li>
        <div class="direction-r">
            <div class="flag-wrapper">
                <span class="flag">{{ item.degree }}</span>
                <span class="time-wrapper">{{ item.time }}</span>
            </div>
            <div class="desc">
                <span>{{ item.university }}</span>
                <span><a href="{{item.url}}">{{ item.department }}</a></span>
            </div>
        </div>
    </li>
{% endfor %}
</ul>

<h2>Experiences</h2>
<ul class="timeline">
{% for item in site.data.experiences %}
    <li>
        <div class="direction-r">
            <div class="flag-wrapper">
                <span class="flag">{{ item.job-title }}</span>
                <span class="time-wrapper">{{ item.time }}</span>
            </div>
            <div class="desc">
                <span><a href="{{item.url}}">{{ item.organization }}</a></span>
                <span>{{ item.location }}</span>
            </div>
        </div>
    </li>
{% endfor %}
</ul>

<h2>Publications</h2>
<ul id="publication-container">
{% for item in site.data.publications %}
    <li>
        <div>
            {% for author in item.Authors %}
            <span>{{ author.Name }}, </span>
            {% endfor %}
            <span>"{{ item.Title }}", </span>
            <span style="font-style: italic">in {{ item.Publication }}, </span>
            <span>{{ item.Date }}</span>
            {% if item.DOI %}
            <span><a href="https://doi.org/{{ item.DOI }}">, DOI: {{ item.DOI }}</a></span>
            {% endif %}
            {% if item.Url %}
            <span><a href="{{ item.Url }}">, [Link]</a></span>
            {% endif %}
            <span>.</span>
        </div>
        {% if item.Keywords %}
        <div class="keyword-item">
            <span class="icon icon--keyword">
                {% include icon-lightbulb.svg %} 
            </span>
            <span>Keywords: </span>
            <span class="tags-container">
                {% for keyword in item.Keywords %}
                <span>{{ keyword }}, </span>
                {% endfor %}
            </span>
        </div>
        {% endif %}
        {% if item.Venue %}
        <div class="location-item">
            <span class="icon icon--location">
                {% include icon-location.svg %}
            </span>
            <span>Venue Location: </span>
            <span>{{ item.Venue }} </span>
        </div>
        {% endif %}
    </li>
{% endfor %}
</ul>