---
layout: page
title: people
permalink: /people/
description: Current and former students and research personnel I have had the privilege to supervise.
nav: true
nav_order: 6
---

# Current Students

<div class="students-grid">
{%- for student in site.data.students.current_students -%}
  <div class="student-card">
    <div class="student-image">
      {%- if student.image -%}
        {%- if student.image contains 'http' -%}
          <img src="{{ student.image }}" alt="{{ student.name }}" class="student-photo">
        {%- else -%}
          <img src="{{ student.image | prepend: '/assets/img/students/' | relative_url }}" alt="{{ student.name }}" class="student-photo">
        {%- endif -%}
      {%- else -%}
        <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzAwIiBoZWlnaHQ9IjMwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMzAwIiBoZWlnaHQ9IjMwMCIgZmlsbD0iI2ZmZmZmZiIvPjx0ZXh0IHg9IjUwJSIgeT0iNTAlIiBmb250LWZhbWlseT0iQXJpYWwsIHNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iNDgiIGZpbGw9IiNjY2NjY2MiIHRleHQtYW5jaG9yPSJtaWRkbGUiIGR5PSIuM2VtIj5Vc2VyPC90ZXh0Pjwvc3ZnPg==" alt="{{ student.name }}" class="student-photo">
      {%- endif -%}
    </div>
    <div class="student-info">
      <h3 class="student-name">
        {%- if student.profile_url -%}
          <a href="{{ student.profile_url }}" target="_blank" rel="noopener noreferrer">{{ student.name }}</a>
        {%- else -%}
          {{ student.name }}
        {%- endif -%}
      </h3>
          <p class="student-program">{{ student.program }}</p>
    </div>
  </div>
{%- endfor -%}
</div>

---

# Research Staff

<div class="students-grid">
{%- for staff in site.data.students.research_staff -%}
  <div class="student-card">
    <div class="student-image">
      {%- if staff.image -%}
        {%- if staff.image contains 'http' -%}
          <img src="{{ staff.image }}" alt="{{ staff.name }}" class="student-photo">
        {%- else -%}
          <img src="{{ staff.image | prepend: '/assets/img/students/' | relative_url }}" alt="{{ staff.name }}" class="student-photo">
        {%- endif -%}
      {%- else -%}
        <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzAwIiBoZWlnaHQ9IjMwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMzAwIiBoZWlnaHQ9IjMwMCIgZmlsbD0iI2ZmZmZmZiIvPjx0ZXh0IHg9IjUwJSIgeT0iNTAlIiBmb250LWZhbWlseT0iQXJpYWwsIHNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iNDgiIGZpbGw9IiNjY2NjY2MiIHRleHQtYW5jaG9yPSJtaWRkbGUiIGR5PSIuM2VtIj5Vc2VyPC90ZXh0Pjwvc3ZnPg==" alt="{{ staff.name }}" class="student-photo">
      {%- endif -%}
    </div>
    <div class="student-info">
      <h3 class="student-name">
        {%- if staff.profile_url -%}
          <a href="{{ staff.profile_url }}" target="_blank" rel="noopener noreferrer">{{ staff.name }}</a>
        {%- else -%}
          {{ staff.name }}
        {%- endif -%}
      </h3>
      <p class="student-program">{{ staff.position }}</p>
    </div>
  </div>
{%- endfor -%}
</div>

---

# Alumni

<ul class="alumni-list">
{%- for student in site.data.students.alumni_students -%}
  <li class="alumni-item">
    <strong>
      {%- if student.profile_url -%}
        <a href="{{ student.profile_url }}" target="_blank" rel="noopener noreferrer">{{ student.name }}</a>
      {%- else -%}
        {{ student.name }}
      {%- endif -%}
    </strong>
    - {{ student.program }} at NYU ({{ student.start_year }}-{{ student.end_year }}) → 
    <strong>{{ student.current_position }}</strong> at {{ student.current_institution }}
  </li>
{%- endfor -%}
</ul>

<style>
.students-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2rem;
  margin: 2rem 0;
}

.alumni-list {
  list-style: none;
  padding: 0;
  margin: 2rem 0;
}

.alumni-item {
  margin-bottom: 1rem;
  padding: 0.5rem 0;
  border-bottom: 1px solid var(--light-bg);
  font-size: 1.1rem;
  line-height: 1.6;
}

.alumni-item:last-child {
  border-bottom: none;
}

.student-card {
  background: var(--card-bg);
  border-radius: 10px;
  padding: 1.5rem;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid var(--border-color);
}

.student-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 20px rgba(0,0,0,0.15);
}

.student-image {
  text-align: center;
  margin-bottom: 1rem;
}

.student-photo {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
  border: 3px solid var(--primary-color);
}


.student-info {
  text-align: center;
}

.student-name {
  margin: 0 0 0.5rem 0;
  color: var(--text-color);
  font-size: 1.3rem;
}

.student-name a {
  color: var(--primary-color);
  text-decoration: none;
  transition: color 0.3s ease;
}

.student-name a:hover {
  color: var(--primary-color);
  text-decoration: underline;
  opacity: 0.8;
}

.student-program {
  margin: 0 0 0.5rem 0;
  color: var(--primary-color);
  font-weight: 600;
  font-size: 1.1rem;
}

.student-research {
  margin: 0 0 0.5rem 0;
  color: var(--text-muted);
  font-style: italic;
}

.student-year {
  margin: 0 0 0.5rem 0;
  color: var(--text-muted);
  font-size: 0.9rem;
}

/* Dark mode support */
@media (prefers-color-scheme: dark) {
  .student-card {
    background: var(--dark-card-bg);
    border-color: var(--dark-border-color);
  }
}

/* Responsive design */
@media (max-width: 768px) {
  .students-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .student-card {
    padding: 1rem;
  }
  
  .student-photo {
    width: 100px;
    height: 100px;
  }
}
</style>
