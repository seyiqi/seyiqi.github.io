# People Page Management

This document explains how to manage the people page on your academic website.

## Overview

The people page showcases current and former students and research personnel you have supervised. It includes:
- **Current Students**: Name, program (PhD/MS/BS), and profile image
- **Research Staff**: Name, position, and profile image
- **Alumni**: Name, program, years of study, research area, current position, institution, and thesis title

## Files Structure

```
_data/students.yml          # People data (current students, research staff, and alumni)
_pages/people.md            # People page layout and styling
assets/img/students/        # Profile images
```

## Adding New People

### 1. Add Student Data

Edit `_data/students.yml` to add new students:

### Image Options

The `image` field supports both local files and URLs:

- **Local files**: Place images in `assets/img/students/` and use just the filename
  - Example: `image: "student_photo.jpg"`
- **URLs**: Use full URLs for external images
  - Example: `image: "https://example.com/photo.jpg"`
- **No image**: If no image is provided, a white placeholder with "User" text will be displayed

**For Current Students:**
```yaml
current_students:
  - name: "Student Name"
    program: "PhD in Data Science"  # Display exactly as entered
    image: "student_photo.jpg"  # optional - local file or URL
    start_year: 2024  # Used internally, not displayed
    research_area: "Research focus area"
    status: "Current"
```

**For Research Staff:**
```yaml
research_staff:
  - name: "Dr. Jane Smith"
    position: "Senior Research Engineer"
    image: "staff_photo.jpg"  # optional - local file or URL
    start_year: 2023
    status: "Current"
    profile_url: "https://janesmith.github.io"
```

**For Alumni:**
```yaml
alumni_students:
  - name: "Dr. Alumni Name"
    program: "PhD"  # or "MS" or "BS"
    image: "alumni_photo.jpg"  # optional - local file or URL
    start_year: 2020
    end_year: 2024
    research_area: "Research focus area"
    current_position: "Current job title"
    current_institution: "Current institution"
    thesis_title: "Thesis title"  # optional
```

### 2. Add Profile Images (Optional)

1. Add student photos to `assets/img/students/`
2. Use the filename in the `image` field of the student data
3. Recommended size: 300x300px or larger
4. Supported formats: JPG, PNG, WebP

### 3. Update Student Status

When a student graduates:
1. Move their entry from `current_students` to `alumni_students`
2. Add `end_year`, `current_position`, and `current_institution`
3. Optionally add `thesis_title`

## Customization

### Styling
The page uses custom CSS embedded in `_pages/students.md`. You can modify:
- Grid layout (currently responsive)
- Card appearance and hover effects
- Colors and typography
- Image sizes and shapes

### Navigation
The students page appears in the main navigation with order 6. To change the order, modify `nav_order` in `_pages/students.md`.

## Example Student Entries

### Current PhD Student
```yaml
- name: "Jane Smith"
  program: "PhD"
  image: "jane_smith.jpg"
  start_year: 2023
  research_area: "Explainable AI in Medical Imaging"
  status: "Current"
```

### Alumni PhD Student
```yaml
- name: "Dr. John Doe"
  program: "PhD"
  image: "john_doe.jpg"
  start_year: 2019
  end_year: 2023
  research_area: "Multimodal Learning for Healthcare"
  current_position: "Research Scientist"
  current_institution: "Google Health"
  thesis_title: "Advanced Neural Networks for Medical Image Analysis"
```

## Notes

- The page automatically handles missing images with placeholder icons
- All styling is responsive and works on mobile devices
- The page supports both light and dark themes
- Student data is stored in YAML format for easy editing
