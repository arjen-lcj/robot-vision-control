# Project Scope

## Status and assumptions

This project is at the planning and repository-scaffold stage. The board roles below are design goals, not completed features. Board revisions, kernel versions, pin availability, display connections, and camera wiring must be verified and recorded before implementation.

## Goal

Build a reproducible multi-board robotics prototype and portfolio project focused on Linux driver development, camera capture, motor control, diagnostics, and PC-side monitoring.

## Planned board roles

- **RK3588B board (4 GB RAM / 32 GB storage) with IMX415 camera:** camera capture, vision experiments, and display.
- **i.MX6ULL Alpha:** Linux driver exercises, diagnostics, logging, and a possible gateway role.
- **STM32F407 Explorer:** motor and encoder control with a local status display.
- **STM32F103 Elite:** optional auxiliary I/O and test node.
- **Host PC:** monitoring, control, and log collection.

These roles depend on the actual board interfaces and connected peripherals.

## Driver and source policy

Keep vendor BSP and kernel sources as external baselines. Write project-owned drivers in this repository and use the relevant Linux kernel frameworks where practical. Keep project device-tree changes, configuration fragments, and any required kernel patches separate and documented; do not edit vendor source files in place.

## Open decisions

- Exact board revisions, OS images, and kernel versions.
- IMX415 module wiring and its compatibility with the selected RK3588 camera pipeline.
- Physical transport between boards, such as UART, CAN, or Ethernet, after checking connectors, transceivers, and electrical levels.
- Motor driver, power requirements, and safe stop behavior.
- The protocol and message format shared by the boards and host application.

## Initial completion criteria

- Record each board revision, software baseline, peripheral connection, and relevant license.
- Provide build, deployment, and validation steps for each project-owned driver or firmware component.
- Demonstrate camera capture, motor/encoder telemetry, board diagnostics, and host-side monitoring as the hardware is verified and integrated.

## Initial non-goals

The first version does not target safety-certified industrial control or fully autonomous navigation.
EOF