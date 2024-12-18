---
layout: default
title: Projects
permalink: /projects

---
<div class="flex flex-col justify-center gap-3 pt-1 pb-12" data-aos="fade-up">
  {% for project in site.projects %}
  <div
    class="w-[80vw] mx-auto bg-[{{ site.bg-colors.gray }}] p-6 rounded-2xl border-2 border-[{{ site.bg-colors.skyBlue }}] space-y-3" data-aos="fade-up"
  >
    <!-- Project Card -->
    <div
      class="flex flex-col md:flex-row justify-start md:justify-between items-start space-y-6 md:space-y-0"
    >
      <!-- Left Section: Title -->
      <div class="flex items-center">
        <h2 class="text-2xl font-montserrat font-bold text-[{{ site.text-colors.base-black }}]">
          {{ project.title }}
        </h2>
      </div>

      <!-- Right Section: Status Tags -->
      <div class="font-inter flex flex-wrap gap-2">
        {% for status in project.status %} {% if status == "active" %}
        <span
          class="bg-green-200 text-green-700 px-4 py-2 rounded-full text-sm font-bold"
          >Active/In Progress</span
        >
        {% elsif status == "open" %}
        <span
          class="bg-orange-200 text-orange-700 px-4 py-2 rounded-full text-sm font-bold"
          >Open for Contribution</span
        >
        {% elsif status == "planning" %}
        <span
          class="bg-yellow-200 text-yellow-700 px-4 py-2 rounded-full text-sm font-bold"
          >Planning</span
        >
        {% endif %} {% endfor %}
      </div>
    </div>

    <!-- Tags Section -->
    <div class="flex flex-wrap gap-2">
      {% for tag in project.tags %}
      <span
        class="bg-blue-200 text-blue-700 px-3 py-1 rounded-full text-sm font-inter font-bold"
        >{{ tag }}</span
      >
      {% endfor %}
    </div>

    <!-- Description Section -->
    <p class="font-inter text-[{{ site.text-colors.base-black }}] text-sm">
      {{ project.short_description }}
    </p>

    <div
      class="flex flex-col md:flex-row justify-start md:justify-between items-start"
    >
      <!-- Technology Icons Section -->
      <div class="flex space-x-3 mb-4 md:mb-0">
        {% for tech in project.tech %} {% assign logo =
        site.data['tech-logo'][tech] %}
        <iconify-icon icon="{{ logo }}" class="text-3xl"></iconify-icon>
        {% endfor %}
      </div>

      <!-- GitHub Button -->
      <a
        href="{{ project.github_url }}"
        class="flex items-center space-x-2 bg-[{{ site.bg-colors.baseBlack }}] text-[{{ site.text-colors.white }}] font-inter px-4 py-2 rounded-lg hover:bg-gray-800"
        target="_blank"
        rel="noopener noreferrer"
      >
        <iconify-icon icon="mdi:github" class="text-2xl"></iconify-icon>
        <span>View on GitHub</span>
      </a>
    </div>
  </div>
  {% endfor %}
</div>
