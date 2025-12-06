# Cardiac-Surgery-Skill-Assessment
AI Based Cardiac Surgery Skill Evaluation Tool

Cardiac Surgery Skill Assessment Using SAM v2 & Motion Analytics

Capstone Project – University of Arizona
Author: Adarsha Nagaraja
GPU Used: NVIDIA A100 (Google Colab)

🚀 Project Overview

This project develops an AI-driven, objective, and scalable surgical skill assessment system for cardiac suturing tasks.
Using SAM v2 for pixel-accurate segmentation and a custom trajectory-analysis pipeline, the system extracts detailed kinematic and coordination metrics that reflect surgical proficiency.

The solution aims to address the limitations of current surgeon training, where evaluations are subjective, inconsistent, and expert-dependent.

🎯 Goal

To build a fully automated suturing skill evaluation pipeline that:
-Tracks needle and forceps behavior from surgical videos
-Computes quantitative motion and coordination metrics
-Normalizes performance across different camera setups
-Prepares the foundation for OSATS-aligned clinical scoring
-Enables fair, repeatable, and data-driven skill evaluation

🧩 System Architecture

The architecture follows a modular sequence:
1-Frame Extraction
2-Input surgical video is decomposed into frames.
3-SAM v2 Segmentation
4-Needle and forceps masks are generated per frame using SAM v2.
5-Trajectory Extraction
6-Centroid positions → motion paths for each instrument.
7-Metric Computation
Path length
Smoothness
Jerk
Orientation variability
Forceps–needle distance
Contact ratio
Synchronization lag
Normalization Layer (WIP)
Corrects pixel-based distortions caused by varying camera setups.
Ensures fair scoring across datasets.


OSATS Mapping (Future)
Convert metric profile → clinical score profile.

🔄 Data Flow
Video → frames.
Frames → SAM v2 masks.
Masks → trajectories.
Trajectories → metrics.
Metrics → normalized score.
Score → OSATS evaluation (future).
This ensures a reproducible and end-to-end automated pipeline.

📊 Extracted Metrics
Category	Metrics.
Motion Quality	Path length, smoothness, jerk.
Precision & Stability	Orientation variability.
Coordination	Forceps–needle distance, synchronization lag.
Engagement	Contact ratio.
Upcoming	Economy of motion, stitch spacing accuracy.

⚠️ Current Limitations
Metrics depend on pixel space, causing variation across cameras.
Needs normalization or depth correction (RGB-D recommended).
Requires expert-validated thresholds and OSATS mapping.
Limited dataset — only one stitch sequence (~480 frames).

📈 Next Steps
Add RGB-D camera support for real-world metric calibration.
Build 3D trajectory reconstruction.
Create larger annotated datasets (needle + forceps + tissue).
Compare results with expert OSATS ratings.
Deploy as an interactive web dashboard.
Implement CI/CD + model monitoring for deployed version.
