---
title: "Undergraduate Thesis - Topological Data Analysis"
date: 2023-05-01T00:00:00+08:00
draft: false
categories: ["research"]
tags: ["topological-data-analysis", "basketball", "machine-learning", "clustering"]
aliases:
  - /files/thesis
description: "Using Topology to Extract Insights from UAAP Basketball Data"
showToc: true
---

**Authors:** Benjamin Louis Ang, Alexander Pino Jr., Dane Lauren Rosario

## Full Manuscript

Click [here](/files/Ang_Pino_Rosario_Manuscript_430.pdf) to read the paper in full.

## Abstract

Basketball is one of the most popular team sports, whose many competitive, well-organized and well-recorded leagues provide rich sources of data frequently used to analyze tactics, strategy, player performance and team composition. A consequence of basketball's team dynamics, comprising five active players per team on the court who may be replaced by substitute players on many occasions per game, is the formation of archetypes; players are categorized into positions based on roles they play, such as point-scoring, rebounding or defense. However, the evolution of game strategy has meant that the three traditional positions, namely—guard, forward, and center, are no longer sufficient to completely describe roles of players within the team.

Understanding the archetypes of basketball players offers an advantage to teams in strategizing against their opponents, and finding and fixing weaknesses in their team composition, whether by adding skills to current players or recruiting new talent. Usually a matter of subjective observation, especially in non-professional leagues such as the collegiate University Athletics Association of the Philippines (UAAP), we undertake the task of finding groups of players who fit in certain positions or archetypes more objectively with mathematical techniques from topological data analysis (TDA).

We use numerical data measuring player performance during the 84th season of the UAAP basketball tournament, with a high number of features per player corresponding to different player actions such as points, rebounds, assists, steals, blocks, turnovers, fouls and shot attempts. Using this high-dimensional dataset as a point cloud, we use Vietoris-Rips filtration to connect nodes representing players from progressively longer distances, discovering the presence of hole complexes that imply groupings or clusters of players. We study our dataset further using the Mapper algorithm which applies dimensionality reduction and clustering to more prominently display topological features as connections between nodes representing multiple players.

We are able to identify four subgroups of players not previously indicated in the five traditional basketball positions; paint dominators, stretch forwards, defensive rebounders, and scrappers. Furthermore, we discover two hole structures of a much larger prominence than others in the mapper plot, associating them with missing archetypes of players. These are three-point plus defensive specialists, and aggressive foul-drawers, whose attributes are currently underrepresented within the league, and thus could make a team to strategize against. We conclude that TDA techniques can identify archetypes of players beyond the traditional classifications and can provide advantageous insights for basketball teams.
