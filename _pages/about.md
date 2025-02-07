---
layout: about
title: about
permalink: /
subtitle: <a href='#'>Affiliations</a>. Address. Contacts. Motto. Etc.

news: true # includes a list of news items
selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page
---

Welcome to the website of the Luck Lab lead by Assist. Professor [Kevin Sebastian Luck](https://www.kevin-luck.com)! We are part of the [Computational Intelligence Group](https://cs.vu.nl/ci/) at the Vrije Universiteit Amsterdam in The Netherlands.

Our group's research is centered broadly on robot learning, with a special focus on
 - Deep Reinforcement Learning for Continuous Control & Robotics
 - Multi- and Cross-Embodiment Learning
 - Co-Design & Co-Optimization of Robot Design and Behaviour
 - Robot Learning Applications to Robot Manipulation and Locomotion

 {% assign members = site.members | where: "team_frontpage", true | sort: "lastname" %}
 <div class="d-flex flex-wrap align-content-stretch justify-content-center m-n2 pt-5 no-gutters">
     {% for member in members %}
         {% assign colsMod6 = forloop.length | modulo: 6 %}
         {% assign colIdMod4 = forloop.index | modulo: 4 %}
         {% if colsMod6 == 1 and colIdMod4 == 1 %}<div class="col-md-2 w-100"></div>{% endif %}
         <div class="col-6 col-sm-3 col-md-2 mb-3">
             <a href="{{ member.url | relative_url }}" class="no-decoration">
                 <div class="card hoverable h-100 m-2">
                     <img src="{{ '/assets/img/' | append: member.profile.image | relative_url }}" class="card-img-top" alt="{{ member.profile.name }}" />
                     <div class="card-body p-2">
                         <div class="card-title m-0">{{ member.title }}</div>
                     </div>
                 </div>
             </a>
         </div>
     {% endfor %}
