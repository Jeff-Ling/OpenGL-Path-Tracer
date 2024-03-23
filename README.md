# OpenGL Path Tracer
CIS 561 Project - A Simple Path Tracer

## Li-Navie
 - Implemented the Lambertian Bidirectional Reflectance Distribution Function (BRDF) in GLSL for rendering perfectly diffuse materials within a path tracing framework.
 - Enhanced the physically based rendering pipeline by coding the evaluation, sampling, and probability density functions for diffuse surfaces, incorporating cosine-weighted hemisphere sampling to accurately simulate the light scattering according to Lambert's Law.
 - Developed the Li_Naive function within the path tracing shader to iteratively compute the light transport equation. This involved calculating the accumulated light energy and ray throughput for each ray bounce, up to a predefined maximum depth.
 - Integrated scene intersection logic to determine the interaction of rays with diffuse surfaces, applying the Lambertian BRDF to simulate realistic light diffusion.
 - Implemented a system for summing up render passes in the main rendering loop, employing a weighted averaging technique to progressively refine the image and achieve a converged, realistic rendering of the Cornell Box scene.

| Sum Up                                                                                                                                               |HDR                                                                                                                                                   |
| ----                                                                                                                                                 | ----                                                                                                                                                 |
| ![](https://github.com/CIS-4610-2024/homework-02-sampling-and-beginning-path-tracing-Jeff-Ling/assets/74678923/80bc85d2-78b6-4713-9d10-bbd1106dc501) | ![](https://github.com/CIS-4610-2024/homework-02-sampling-and-beginning-path-tracing-Jeff-Ling/assets/74678923/ef92dc0e-0b67-4ed0-8660-2cc92624404b) |


## Li_Direct
 - Developed and integrated a new lighting estimation function, `Li_Direct`, into a path tracer to accurately simulate direct lighting from various light sources, enhancing scene realism.
 - Implemented specular reflection and transmission BSDFs, enabling the rendering of complex materials with reflective and transmissive properties, such as mirrors and glass.
 - Extended the path tracer to handle dielectric materials using the Fresnel Dielectric Evaluation, providing physically accurate reflections and transmissions based on the material's refractive index.
 - Programmed custom light sampling functions, including DirectSampleAreaLight, DirectSamplePointLight, and DirectSampleSpotLight, to efficiently sample light sources, improving rendering quality and reducing noise.

| Specular BRDFs | Handling dielectric materials |
| ----           | ----                          |
| ![image](https://github.com/CIS-4610-2024/homework-03-direct-lighting-and-specular-materials-Jeff-Ling/assets/74678923/9a9c134f-a891-4821-8149-a977e9465e75)   | ![image](https://github.com/CIS-4610-2024/homework-03-direct-lighting-and-specular-materials-Jeff-Ling/assets/74678923/9e712909-7fe1-4359-bc5b-69aab7806e12) |

| DirectSamplePointLight | DirectSampleSpotLight |
| ----                   | ----                  |
| ![image](https://github.com/CIS-4610-2024/homework-03-direct-lighting-and-specular-materials-Jeff-Ling/assets/74678923/5feb6e5e-60ea-4706-90e8-c4fcafb4a910)  | ![image](https://github.com/CIS-4610-2024/homework-03-direct-lighting-and-specular-materials-Jeff-Ling/assets/74678923/1676d3f7-4cb8-4aa5-a2f7-1aec1d622128) | 

| Direct Lighting Example Renders |
| ----                            |
| ![image](https://github.com/CIS-4610-2024/homework-03-direct-lighting-and-specular-materials-Jeff-Ling/assets/74678923/2c2b2f5b-7da1-4f88-b202-482af79fbcad) |

## Li_DirectMIS
 - Implemented an advanced path tracing integrator utilizing multiple importance sampling (MIS) to optimize the direct illumination estimation in scenes with varying light source sizes and microfacet materials. This technique significantly improved the realism and efficiency of rendered images by balancing the contribution of light sources and surface reflections.
 - Enhanced the path tracer with the capability to accurately render microfacet materials, employing provided microfacet BRDF models. This addition allowed for the realistic portrayal of surfaces with different roughness levels, capturing the nuanced interplay of light with complex materials.
 - Developed the Li_DirectMIS function to generate and evaluate two types of lighting samples: direct light source samples and BSDF-based samples. This approach enabled the accurate representation of direct lighting effects from diverse light sources, including area and point lights, in scenes with highly glossy to rough surfaces.
 - Integrated the Power Heuristic method to compute optimal weights for each lighting sample, ensuring energy conservation and reducing noise in the final render. This method effectively balanced the contributions of different sampling strategies, leading to more consistent and visually pleasing results.

| | |
| ----           | ----                          |
| ![image](https://github.com/CIS-4610-2024/homework-04-multiple-importance-sampling-Jeff-Ling/assets/74678923/8fc7005d-2384-4b5e-8093-ce64ddfca87f)   | ![image](https://github.com/CIS-4610-2024/homework-04-multiple-importance-sampling-Jeff-Ling/assets/74678923/3b8dce3e-f17c-4fe7-a28f-559a680d1595) |
