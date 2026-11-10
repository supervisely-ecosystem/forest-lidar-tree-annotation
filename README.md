<div align="center" markdown>

# Forest LiDAR Tree Annotation (FOR-instance CULS plot)

A UAV LiDAR forest plot, ready for labeling individual trees with 3D cuboids and point masks.

[![GitHub release](https://img.shields.io/github/v/release/supervisely-ecosystem/forest-lidar-tree-annotation)](https://github.com/supervisely-ecosystem/forest-lidar-tree-annotation/releases)
[![views](https://app.supervisely.com/img/badges/views/supervisely-ecosystem/forest-lidar-tree-annotation.png)](https://supervisely.com)
[![downloads](https://app.supervisely.com/img/badges/downloads/supervisely-ecosystem/forest-lidar-tree-annotation.png)](https://supervisely.com)

![Forest LiDAR plot in the 3D point cloud editor](https://github.com/supervisely-ecosystem/forest-lidar-tree-annotation/releases/download/v1.0.0/cover.png)

</div>

## Overview

This sample project contains one point cloud: plot 1 of the CULS site from the FOR-instance dataset, a Riegl UAV laser scan of a conifer stand in the Czech Republic. It has 1,816,672 points over about 28 x 32 m, with crowns up to about 29 m above the ground. The project has two classes and no labels:

- `tree`, shape **Cuboid**, for one 3D box per tree;
- `tree_points`, shape **Point Cloud**, for per-point tree masks.

Use it to:

- explore a dense forest scan in the 3D point cloud editor: the Top, Side, Front and Perspective views, coloured by height;
- label trees one by one with cuboids placed by the 3D AI Assistant (Smart Lasso 3D), and adjust them by hand;
- draw point masks of single trees with the Point Cloud Pen.

## How to Use This Project

1. Click **Get project** in the Supervisely Ecosystem and choose a team and a workspace.
2. Open the `CULS plot 1` dataset and the point cloud `plot_1_annotated.pcd` in the 3D point cloud editor.
3. Pick the class `tree` and label the trees, by hand or with the 3D AI Assistant.

See the complete workflow in [Label Trees in Forest LiDAR with AI 3D Cuboids](https://docs.supervisely.com/use-cases/forest-lidar-tree-annotation).

## Download

Download the project in Supervisely format: [project.zip](https://github.com/supervisely-ecosystem/forest-lidar-tree-annotation/releases/download/v1.0.0/project.zip).

## Dataset Source and License

The point cloud is one plot of **FOR-instance: a UAV laser scanning benchmark dataset for semantic and instance segmentation of individual trees** by Puliti, S., Pearse, G., Surový, P., Wallace, L., Hollaus, M., Wielgosz, M. and Astrup, R., published on [Zenodo](https://doi.org/10.5281/zenodo.8287792). It is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

Citation:

> Puliti, S., Pearse, G., Surový, P., Wallace, L., Hollaus, M., Wielgosz, M., Astrup, R. (2023). FOR-instance: a UAV laser scanning benchmark dataset for semantic and instance segmentation of individual trees. arXiv:2309.01279. Data: https://doi.org/10.5281/zenodo.8287792

Changes:

- Only `CULS/plot_1_annotated.las` was taken from the dataset; the file name is kept.
- It was converted from LAS to binary PCD with the fields `x`, `y`, `z` and `intensity` (27.7 MB). The other LAS fields, including the source's `classification`, `treeID` and `treeSP` labels, are not included.
- The coordinates were recentred: the minimum of each axis was subtracted, so the plot starts at the origin. The points themselves are unchanged.
- The classes `tree` and `tree_points` were added; the project has no labels.
