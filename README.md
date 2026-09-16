[English](README.md) · [简体中文](README.zh-CN.md)

<div align="center">

# Elder-Friendly Offline Games

### An anonymized product-engineering case study

A cross-platform set of accessible, offline recreational games for older adults in public-service waiting environments.

`SwiftUI` · `Flutter` · `iOS / iPadOS` · `Android` · `Windows`

</div>

<p align="center">
  <img src="assets/clock-reading-concept.svg" width="520" alt="Original neutral concept for a large-type clock-reading game with four accessible answer controls">
</p>

## Product question

How can a short waiting period become a calm, approachable interaction for an older adult without requiring an account, a network connection or unfamiliar gestures?

The prototype explores that question through seven recreational mini-games with four difficulty levels, large text, high contrast, generous targets, optional timing and device-local speech.

## Product decisions

| Decision | Reason |
|---|---|
| No account or sign-in | Removes setup friction and avoids collecting identity data |
| Offline-first operation | Keeps the core experience available without network access |
| No camera, microphone or location | Minimizes permissions and privacy exposure |
| Large controls and high contrast | Reduces reading and touch precision demands |
| Gentle error feedback | Avoids shaming or rushing the player |
| Difficulty resets for a new player | Prevents one person's settings from surprising the next person |
| Pause during feedback and backgrounding | Keeps the timer from punishing non-play time |

## Prototype scope

- seven mini-games, including memory, sequencing, visual search, color-word interference, clock reading, categorization and spatial recall;
- four difficulty levels with optional challenge timing;
- SwiftUI implementation for iOS/iPadOS;
- Flutter implementation shared across Android and Windows;
- local settings, offline speech when available, and no cloud score service;
- build, interaction and release checks across the supported prototype targets.

## Engineering considerations

### Session state and shared use

The intended setting can involve one person using the device after another. Resetting difficulty for a new player is therefore part of the session boundary: a previous player's choices should not unexpectedly increase the next person's task difficulty. This decision connects the game rules to the way the product is actually used.

The prototype also separates active play from feedback and background time. Pausing during an answer response gives the player time to read or hear it; pausing when the app backgrounds avoids treating an interruption as playing time. These are interaction-state decisions, not merely visual styling.

### Timing and feedback

Optional timing serves a different purpose from the core recreational experience. Large controls and high contrast reduce the effort needed to act; gentle feedback makes an incorrect answer something the player can respond to without being hurried. The timer behavior needs to remain consistent with those choices, which is why feedback and non-play intervals are part of the pause boundary.

### Local data and device capabilities

The public prototype scope includes local settings and no cloud score service. With no account, it does not need an identity-based setup flow; with no required camera, microphone or location access, the core games avoid those permission dependencies. Device-local speech is available where the device supports it, so offline speech capability remains a device-dependent part of the experience.

### Two interface stacks, a common product specification

SwiftUI serves iOS and iPadOS, while Flutter provides the Android and Windows implementation. The common specification is expressed through game rules, difficulty levels, readable controls, feedback and pause behavior. Build, interaction and release checks are recorded for the supported prototype targets; that scope does not establish compatibility with every device or prove a health benefit.

## Safety and privacy boundary

This is a recreational interaction prototype. It does not diagnose a condition, estimate cognitive age, rank a person or claim to prevent or treat disease. It does not require names, phone numbers, financial information or customer records.

## Rights-safe public version

This case study intentionally removes institutional names, logos, posters, staff instructions, delivery details, device identifiers, authorization files and any wording that could imply organizational endorsement. The private production materials are not included in this repository.

Until ownership and publication permission are confirmed, the original working title and client-specific visual identity remain private.

## My contribution

I worked across product definition, accessibility decisions, game rules, multi-platform implementation, test design, failure review and release validation. AI tools assisted implementation and debugging; product judgments and public claims were checked against the working builds and local records.

## Rights

Original case-study writing and neutral presentation created for this repository © 2026 David Deng. All rights reserved. This repository does not license private source code, client-specific interfaces, original question banks, deployment files or authorization systems.
