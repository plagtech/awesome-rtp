# Awesome RTP 🤖

> A curated list of robots, devices, SDKs, and tools compatible with the
> [Robot Task Protocol (RTP)](https://github.com/plagtech/rtp-spec) —
> the open standard for AI agents to hire and pay physical robots via x402.

[![RTP](https://img.shields.io/badge/protocol-RTP_1.0-blue)](https://github.com/plagtech/rtp-spec)
[![x402](https://img.shields.io/badge/payment-x402-green)]()
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

---

## Contents

* [Automaton Oracle](https://automaton-oracle.xyz) - Sovereign x402 crypto intelligence oracle. 9 paid endpoints on Base mainnet: prices, signals, DeFi, whale scanner, full intelligence synthesis. Self-replicating.
- [Protocol](#protocol)
- [Gateways](#gateways)
- [SDKs](#sdks)
- [Reference Hardware](#reference-hardware)
- [Compatible Devices](#compatible-devices)
  - [Industrial Robots](#industrial-robots)
  - [Mobile Robots](#mobile-robots)
  - [Drones](#drones)
  - [Raspberry Pi](#raspberry-pi)
  - [IoT & Smart Devices](#iot--smart-devices)
  - [Microcontrollers](#microcontrollers)
- [Examples & Demos](#examples--demos)
- [Tools](#tools)
- [Related Standards](#related-standards)
- [Community](#community)

---

## Protocol

- [RTP Specification](https://github.com/plagtech/rtp-spec) —
  RTP 1.0 draft specification. Task envelope schema, capability
  vocabulary, state machine, payment standard, and discovery protocol.

---

## Gateways

| Gateway | Chains | Docs | Status |
|---------|--------|------|--------|
| [Spraay Gateway](https://gateway.spraay.app) | Base, Arbitrum, Ethereum, Polygon, Unichain + 7 more | [docs.spraay.app](https://docs.spraay.app) | ✅ Live |

---

## SDKs

### TypeScript / JavaScript

- [rtp-sdk](https://github.com/plagtech/rtp-sdk) —
  Official TypeScript SDK. `RTPDevice` for robot operators,
  `RTPClient` for agents. Includes full CLI wizard.
```bash
  npm install @spraay/rtp-sdk
```

### Python

- [rtp-python-sdk](https://github.com/plagtech/rtp-python-sdk) —
  Official Python SDK. Async, Raspberry Pi and Arduino bridge support.
```bash
  pip install spraay-rtp
```

---

## Reference Hardware

| Repo | Hardware | Capabilities | Language |
|------|----------|-------------|----------|
| [rtp-pi-demo](https://github.com/plagtech/rtp-pi-demo) | Raspberry Pi 4 + SG90 servo | pick, place, scan, move | TypeScript |
| [rtp-pi-demo (Python)](https://github.com/plagtech/rtp-python-sdk/blob/main/examples/pi_servo_robot.py) | Raspberry Pi 4 + SG90 servo | pick, place, scan, move | Python |
| [rtp-xmtp-mesh](https://github.com/plagtech/rtp-xmtp-mesh) | Any XMTP-capable device | any | TypeScript |

---

## Compatible Devices

### Industrial Robots

| Device | Connection | SDK | Notes |
|--------|-----------|-----|-------|
| Universal Robots UR3/UR5/UR10 | SSH → webhook | ✅ Direct | Linux onboard |
| Fetch Robotics | SSH → webhook | ✅ Direct | ROS2 + Linux |
| Rethink Robotics Sawyer | SSH → webhook | ✅ Direct | Linux onboard |
| KUKA KR Series | Ethernet → server | ⚠️ Bridge | KUKA.Ethernet KRL |
| Fanuc R Series | Ethernet → server | ⚠️ Bridge | FANUC FOCAS |
| ABB IRB Series | REST API → server | ⚠️ Bridge | ABB Robot Web Services |
| Yaskawa Motoman | Ethernet → server | ⚠️ Bridge | MotoPlus SDK |

### Mobile Robots

| Device | Connection | SDK | Notes |
|--------|-----------|-----|-------|
| AgileX Scout | SSH → webhook | ✅ Direct | Linux + ROS2 |
| Clearpath Husky | SSH → webhook | ✅ Direct | ROS2 compatible |
| Boston Dynamics Spot | SSH → webhook | ✅ Direct | Spot SDK + Linux |
| iRobot Create 3 | SSH → webhook | ✅ Direct | ROS2 onboard |

### Drones

| Device | Connection | SDK | Notes |
|--------|-----------|-----|-------|
| ArduPilot custom | SSH → webhook | ✅ Direct | Companion computer |
| PX4 custom | SSH → webhook | ✅ Direct | Companion computer |
| Skydio X2 | REST API → server | ⚠️ Bridge | Skydio API |
| DJI Matrice | SDK → mobile/server | ⚠️ Bridge | DJI SDK |

### Raspberry Pi

| Setup | Capabilities | Notes |
|-------|-------------|-------|
| Pi 4 + SG90 servo | pick, place, scan, move | $79 total — [setup guide](https://github.com/plagtech/rtp-pi-demo) |
| Pi 4 + stepper motor | move, deliver | Add A4988 driver board |
| Pi 4 + relay board | dispense, charge | Control any AC/DC device |
| Pi 4 + Pi Camera | capture, scan, inspect | OpenCV for vision tasks |
| Pi Zero 2W | any | Ultra-low cost edge device |
| Pi 4 + Arduino (serial) | any Arduino capability | Bridge pattern |

### IoT & Smart Devices

| Device | Capability | Connection | Notes |
|--------|-----------|-----------|-------|
| Smart lock | unlock, lock | webhook | REST API bridge |
| EV charger (OCPP) | charge, dispense | webhook | OCPP protocol bridge |
| Vending machine | dispense | webhook | Serial or REST |
| 3D printer (OctoPrint) | print | webhook | OctoPrint REST API |
| CNC machine (Mach3/4) | move, weld, assemble | webhook | Windows or Linux |

### Microcontrollers

| Device | Bridge | Notes |
|--------|--------|-------|
| Arduino Uno/Mega | Raspberry Pi | Serial bridge — [example](https://github.com/plagtech/rtp-python-sdk/blob/main/examples/arduino_bridge.py) |
| ESP32 | Raspberry Pi or direct WiFi | Can run minimal HTTP server |
| ESP8266 | Raspberry Pi | Serial bridge |
| STM32 | Raspberry Pi | Serial/SWD bridge |

---

## Examples & Demos

| Repo | Description | Language |
|------|-------------|----------|
| [rtp-pi-demo](https://github.com/plagtech/rtp-pi-demo) | Raspberry Pi servo — full pick/place/scan demo | TypeScript |
| [rtp-xmtp-mesh](https://github.com/plagtech/rtp-xmtp-mesh) | 3-robot XMTP mesh coordination demo | TypeScript |
| [rtp-python-sdk/examples](https://github.com/plagtech/rtp-python-sdk/tree/main/examples) | Pi servo, agent test, Arduino bridge | Python |

---

## Tools

| Tool | Description |
|------|-------------|
| [rtp-device CLI](https://github.com/plagtech/rtp-sdk) | `rtp-device init/start/status/update` |
| [Spraay Dashboard](https://spraay.app) | Web UI for robot operators |
| [Spraay MCP Server](https://github.com/plagtech/spraay-x402-mcp) | MCP server exposing RTP tools to AI agents |

---

## Related Standards

| Standard | Description | Relationship |
|----------|-------------|-------------|
| [x402](https://github.com/coinbase/x402) | HTTP payment protocol | RTP uses x402 as payment layer |
| [MCP](https://modelcontextprotocol.io) | Model Context Protocol | RTP tools exposed via MCP |
| [XMTP](https://xmtp.org) | Web3 messaging protocol | RTP XMTP connection type |
| [ERC-8004](https://eips.ethereum.org/EIPS/eip-8004) | On-chain agent registry | RTP robots registered as agents |

### Ecosystem Projects

| Project | Description | Relationship to RTP |
|---------|-------------|-------------------|
| [peaq](https://peaq.xyz) | L1 blockchain for DePIN | Infrastructure layer — complementary |
| [Auki](https://auki.network) | Spatial computing for robots | Coordination layer — complementary |
| [Coinbase CDP](https://docs.cdp.coinbase.com) | Crypto dev platform | RTP uses CDP as x402 facilitator |
| [Virtuals Protocol](https://virtuals.io) | AI agent framework | RTP robots hireable by Virtuals agents |

---

## Community

- **Twitter/X:** [@Spraay_app](https://twitter.com/Spraay_app)
- **Farcaster:** [@plag](https://warpcast.com/plag)
- **GitHub:** [github.com/plagtech](https://github.com/plagtech)
- **Docs:** [docs.spraay.app](https://docs.spraay.app)

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## License

[CC0 1.0](LICENSE) — public domain.

---

*Maintained by [Spraay Protocol](https://spraay.app)*