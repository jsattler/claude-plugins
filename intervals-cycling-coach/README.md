# Cycling Coach Plugin

Personal cycling performance coach powered by your Intervals.icu data. Designed for endurance cyclists and gran fondo riders.

## What it does

This plugin turns Claude into your personal cycling coach. It connects to your Intervals.icu account to analyze your training data and provide expert coaching advice.

## Commands

| Command          | Description                                                        |
| ---------------- | ------------------------------------------------------------------ |
| `/onboarding`    | First-time setup — reviews your fitness and establishes your goals |
| `/coach`         | Open-ended coaching conversation on any training topic             |
| `/analyze-ride`  | Deep dive analysis of a specific ride                              |
| `/weekly-review` | Review the past week's training load, intensity, and progress      |
| `/plan-week`     | Get a personalized training plan for the upcoming week             |
| `/plan-workout`  | Design a specific workout for today or a given day                 |

## Setup

### Prerequisites

This plugin requires the **[Intervals.icu MCP server](https://github.com/mvilanova/intervals-mcp-server)** to be installed and configured separately. Follow the install instructions in the linked repository to set up the MCP server with your Intervals.icu API key and athlete ID. Make sure it is connected and working before using the plugin commands.

### Get started

After installing the plugin, run `/onboarding` to set up your coaching profile and goals. Then use `/weekly-review` each week to track progress and `/plan-week` to get your upcoming training.

## Coaching Philosophy

The coach follows evidence-based endurance training principles:

- **Polarized training**: ~80% easy / ~20% hard intensity distribution
- **Progressive overload**: Gradual, sustainable fitness building (3-7 TSS/week ramp rate)
- **Recovery-first**: Training adaptations happen during rest, not during the workout
- **Data-informed**: Every recommendation is grounded in your actual training data
- **Periodization**: Structured phases (base → build → peak → taper) aligned to your goals
