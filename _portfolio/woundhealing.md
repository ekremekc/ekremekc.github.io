---
title: "Wound Healing"
excerpt: "Wound healing is a diffusion driven, millennium old phenomenon occurring in almost every creature.<br/><img src='/images/projects/woundHealing//wound_healing.gif' width='600' style='border:1px solid #000000'>"
collection: portfolio
---

<br/><img src='/images/projects/woundHealing//wound_healing.gif' width='600' style='border:1px solid #000000'>

Overview
=========
Wound healing is a diffusion driven, millennium old phenomenon occurring in almost every creature. The edge of the wound (the unwounded part) gradually migrates towards the center of the wound, driven by diffusion mechanism, and proliferating cells reproduce at their current locations via a logistic profile. We model the wound healing over different cases studies and provide estimations based on the diffusion coefficient and proliferation rate. We further recommend how to tweak these to design better and quick treatment techniques using various healing agents.

In this project, we also develop nonlinear FEM solver to solve nonlinear diffusion equation:

$$\frac{\partial \phi}{\partial t} =  D\nabla \cdot (\phi/\phi_0)^p \nabla \phi + s\phi (1-\phi/\phi_0).$$

We use FEniCSx to treat this equation and nonlinearities arising from the second term in the right-hand side. We introduced new spatial healing parameter for better quantification for wound healing. If you want to read more, please refer our paper in Biomechanics and Modeling in Mechanobiology journal:

* [A spatial healing metric for wound healing modeling](https://ekremekc.github.io/files/articles/2025BMM.pdf)