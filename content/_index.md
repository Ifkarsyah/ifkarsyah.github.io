---
# Leave the homepage title empty to use the site title
title: ""
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ""
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/resume.pdf
  - block: markdown
    content:
      title: '📚 Knowledge Garden'
      subtitle: ''
      text: |-
        With my background in computer science, I dream a life where I master the art of simplicity, harmoniously managing my possessions, relationships, and knowledge, while continually growing and contributing to both the tech community.

        My mission is to:

        1. **Simplify Complexity**: Utilize my computer science knowledge to streamline processes, eliminate clutter, and bring clarity to the intricate challenges I encounter in my personal and professional life.
        2. **Excel in Software Engineering**: Excel in my software engineering career by continually expanding my skills, staying up-to-date, and delivering impactful solutions that make a difference in the lives of users.
        3. **Champion Personal Knowledge Management**: Dedicate myself to mastering personal knowledge management, seamlessly integrating physical and digital assets, organizing information, and harnessing the power of well-structured knowledge to drive innovation and personal growth.
        4. **Share Wisdom**: Actively contribute to the tech community by sharing my expertise, insights, and experiences, inspiring others to lead simpler, more fulfilling lives while leveraging technology's potential.
        
        Please reach out to collaborate 😃
  - block: collection
    id: projects
    content:
      title: Recent Projects
      filters:
        folders:
          - projects
    design:
      view: article-grid
      columns: 3

  - block: collection
    id: blogs
    content:
      title: Recent Articles
      subtitle: ''
      text: ''
      count: 3
      filters:
        folders:
          - blogs
    design:
      view: date-title-summary

---
