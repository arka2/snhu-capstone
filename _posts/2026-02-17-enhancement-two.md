---
layout: post
title: "Enhancement Two - Rendering with OpenGL"
author: "Arka Tu"
categories: projects
tags: [projects]
image: header-02.png
---
[GitHub Repository](https://github.com/arka2/opengl-rendering)

## Briefly describe the artifact. What is it? When was it created?
This artifact was created in 2025 when I took CS-330 Computer Graphics and Visualization at SNHU. It’s written in C++ and uses OpenGL to render 3D meshes, textures, and lights to the screen.

## Justify the inclusion of the artifact in your ePortfolio. Why did you select this item? What specific components of the artifact showcase your skills and abilities in software development? How was the artifact improved?
Due to my interest in technical art, I wanted to come back to this project. During the CS-330 course, I came across a page on Learn OpenGL (de Vries, n.d.) detailing shadow mapping, but the course didn’t have us implement cast shadows. It was something I wanted to try, so I decided I could do so during my capstone. Originally, I needed various algorithms to render each fragment correctly, and, for this enhancement, I needed to use an algorithm to calculate the cast shadows. The implementation of these algorithms shows my ability to use them effectively. I also use data structures to hold necessary rendering data, such as the structs used in the main fragment shader to hold light source data and material data.

This project was improved by my implementing cast shadows. I generated a depth map, which tracks what fragments are in the point light's view. Using that depth map, the shadow algorithm compares two depths the depth of an an object that's closest to the light and the depth that's currently being rendered. If the current depth is greater than the closest depth, then that fragment is in shadow. However, these shadows are rendered based on a directional light, not a point light. An improvement I would like to make is rendering the shadows based on a point light. The shadows will be calculated similarly, but instead of using one depth map, the point shadows will use six depth maps, each mapped to one face of a cube map.

Additionally, I refactored the project. I combined the shape data into one class, as the half-cylinder data was separate from the rest of the mesh data. As I was implementing the shadows, I also ended up with duplicate code. While refactoring, I removed the duplicate code.


## Did you meet the course outcomes you planned to meet with this enhancement in Module One? Do you have any updates to your outcome-coverage plans?
The course outcomes I planned to meet with this artifact were:
1. Employ strategies for building collaborative environments that enable diverse audiences to support organizational decision making in the field of computer science
2. Design, develop, and deliver professional-quality oral, written, and visual communications that are coherent, technically sound, and appropriately adapted to specific audiences and contexts
3. Design and evaluate computing solutions that solve a given problem using algorithmic principles and computer science practices and standards appropriate to its solution, while managing the trade-offs involved in design choices (data structures and algorithms)
4. Demonstrate an ability to use well-founded and innovative techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value and accomplish industry-specific goals (software engineering/design/database)

I met Course Outcomes 1 and 2 by refactoring the project. Cleaner and clearer code allows teams to more easily make decisions and allows team members to communicate more easily with one another. Time spent sorting through messy code is reduced, and, as a result, efficiency is improved.

I met Course Outcome 3 by adding an algorithm to calculate cast shadows. Cast shadows are standard in video games now, so, as I’m interested in game development and rendering pipelines, it is helpful to understand how those cast shadows can be calculated and rendered. One trade-off I had to manage was additional difficulty in rendering point shadows. This requires rendering additional textures and additional code and algorithms. As a result, I settled for rendering the directional shadows. Another trade-off was considering performance. The shadows in this project are hard shadows, and there aren't many objects being rendered. This doesn't heavily affect performance, but if I implemented soft shadows or rendered more objects, I might need to reduce the depth map resolution or use fewer objects.

I met Course Outcome 4 by demonstrating my ability to use OpenGL to render to the screen. Various software use OpenGL for rendering, including Unity and Blender. By demonstrating my understanding of OpenGL, I gain a better understanding of the software that use it.


## Reflect on the process of enhancing and modifying the artifact. What did you learn as you were creating it and improving it? What challenges did you face?
The biggest challenge I faced while enhancing this artifact was simply rendering the shadows. I was able to render the depth map itself without much issue, but I couldn’t figure out why the shadows weren’t rendering. I had to reorder parts of my code as I had faulty rendering logic early on, and I ended up learning more about how information is passed to the shaders. But even after doing that, the shadows wouldn’t render. After about four days of debugging, I finally found out that I was using the wrong file path. After I changed that, it worked perfectly.

Even though I didn’t implement it fully, I also started learning about how point shadows are calculated. A depth map is rendered to each face of a cube, and the projection of that face is used to calculate which fragments need to use that depth map.

## References
de Vries, J. (n.d.). Shadow Mapping. Learn OpenGL. https://learnopengl.com/Advanced-Lighting/Shadows/Shadow-Mapping