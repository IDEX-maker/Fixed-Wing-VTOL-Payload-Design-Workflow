# AERO-VTOL QuadPlane Studio — Operator’s Manual & Technical Reference Guide

**Document ID:** `AERO-VTOL-MAN-2026-REV5`
**Target Platform:** Fixed-Wing Lift-and-Cruise VTOL (QuadPlane & Coaxial Octo-QuadPlane)
**Target 3D Printer:** Anycubic Kobra S1 Max (350 x 350 x 350 mm Build Volume)
**Autopilot Compatibility:** PX4 Autopilot v1.14 – v1.17+ (`SYS_AUTOSTART 13000`)

## Approved Drone Component Suppliers Directory (20 Categories)

| Category | Supplier / Brand | Flagship QuadPlane Components & Models | Website |
| --- | --- | --- | --- |
| Sensors | **MicoAir Tech** | MTF-02 / MTF-02P / MTF-01 Optical Flow & ToF Rangefinders, MicoVIO, MicoAir743v3 FC, 55A/70A AM32 ESCs, MG-F10 GNSS & RTK | https://micoair.com/en |
| Flight Controllers | **MicoAir Tech (Autopilots)** | MicoAir743v3, MicoAir743-AIO-45A, NxtPX4v2 (Native PX4 & ArduPilot support) | https://micoair.com/en |
| Flight Controllers | **Holybro (Autopilots & Full Ecosystem)** | Pixhawk 6X / 6X Pro, Pixhawk 6C / 6C Mini, Durandal H7, Kakute H7 & Pix32 v6 Autopilots | https://holybro.com/ |
| Flight Controllers | **CUAV Tech** | CUAV X7+ Pro, Pixhawk V6X, Nora+ H7 Dual/Triple-Redundant IMU Autopilots | https://www.cuav.net/en/ |
| Flight Controllers | **CubePilot (Hex)** | Cube Orange+, Cube Blue H7 (NDAA), Kore Carrier Boards for VTOL QuadPlanes | https://www.cubepilot.com/ |
| Flight Controllers | **Matek Systems** | H743-WING V3, F405-VTOL, DroneCAN AP_Periph Airspeed & Power Nodes | https://www.mateksys.com/ |
| Companion SBCs | **Raspberry Pi Ltd** | Raspberry Pi 5 (8GB/16GB), Compute Module 5 (CM5) & CM4, Raspberry Pi Zero 2 W for MAVROS / ROS 2 / MAVLink routing | https://www.raspberrypi.com/ |
| Companion SBCs | **NVIDIA (Jetson Embedded)** | Jetson Orin Nano Super (67 TOPS), Orin NX (100 TOPS), Jetson AGX Orin for onboard AI vision, VIO & obstacle avoidance | https://developer.nvidia.com/embedded-computing |
| Companion SBCs | **Holybro (Jetson & RPi CM4 Baseboards)** | Pixhawk Jetson Baseboard (Orin NX/Nano + Pixhawk 6X) & Pixhawk Raspberry Pi CM4 Baseboard integrated companion carriers | https://holybro.com/collections/autopilot-flight-controllers |
| Companion SBCs | **Radxa (RPi Equivalent SBCs)** | ROCK 5B / 5B+ (RK3588 8-Core 6 TOPS NPU), Radxa CM5, Radxa Zero 3W ultra-light UAV companion boards | https://radxa.com/ |
| Companion SBCs | **Orange Pi (Shenzhen Xunlong)** | Orange Pi 5 Pro / 5 Max / 5 Plus (Rockchip RK3588S/RK3588), Orange Pi Zero 2W RPi-form-factor alternatives | http://www.orangepi.org/ |
| Companion SBCs | **Khadas** | VIM4 (Amlogic A311D2 + NPU) & Edge2 (RK3588S) ultra-thin credit-card SBCs with native MIPI-CSI camera & PCIe | https://www.khadas.com/ |
| Companion SBCs | **Hardkernel (ODROID)** | ODROID-M1S, ODROID-M2 (RK3588S2), ODROID-C4 & XU4 ruggedized UAV companion SBCs | https://www.hardkernel.com/ |
| Companion SBCs | **Seeed Studio (Carrier Boards & SBCs)** | reComputer J30/J40 Mini Jetson Orin Carrier Boards, Raspberry Pi CM4/CM5 UAV carrier boards & XIAO micro-modules | https://www.seeedstudio.com/ |
| Companion SBCs | **ModalAI (NDAA UAV Companion Computers)** | VOXL 2 & VOXL 2 Mini (Qualcomm QRB5165 15 TOPS + integrated PX4 DSP), VOXL CAM VIO/SLAM & 5G BVLOS modules | https://www.modalai.com/ |
| Companion SBCs | **Auterion (Skynode UAV Mission Computers)** | Skynode X & Skynode S all-in-one PX4 FMUv6X + companion mission computer, LTE/5G link & AuterionOS | https://auterion.com/ |
| Companion SBCs | **Qualcomm (Robotics RB3 / RB5 Platforms)** | Dragonwing RB3 Gen 2 & Robotics RB5 (QRB5165) low-SWaP heterogeneous compute & AI vision platforms for drones | https://www.qualcomm.com/products/internet-of-things/industrial/industrial-automation/robotics |
| Companion SBCs | **Connect Tech (UAV Jetson Carriers)** | Hadron, Boson for FRAMOS & Photon ultra-small ruggedized NVIDIA Jetson Orin NX / Nano carrier boards for UAV payloads | https://connecttech.com/ |
| Companion SBCs | **BeagleBoard.org** | BeagleY-AI (RPi5 form factor, TI AM67A 4 TOPS), BeagleV-Fire (RISC-V + FPGA) & BeagleBone Blue robotics SBCs | https://www.beagleboard.org/ |
| Companion SBCs | **Banana Pi (BPI / Sinovoip)** | BPI-M7 (RK3588 6 TOPS NPU), BPI-M5, BPI-M4 Berry & BPI-CM4 RPi-equivalent SBCs and compute modules | https://www.banana-pi.org/ |
| Companion SBCs | **FriendlyElec (NanoPi)** | NanoPi R6C / R6S, NanoPC-T6 (RK3588 PCIe/M.2) & ultra-compact NanoPi NEO3/ZeroPi telemetry companion boards | https://www.friendlyelec.com/ |
| Companion SBCs | **ASUS IoT (Tinker Board)** | Tinker Board 3N, Tinker Board 2S & PE1000N (Jetson Orin) industrial-temperature RPi-footprint SBCs | https://tinker-board.asus.com/ |
| Companion SBCs | **PINE64** | Quartz64 Model A/B, SOQuartz (CM4-compatible module), RockPro64 & Star64 (RISC-V) open-hardware SBCs | https://www.pine64.org/ |
| Companion SBCs | **Libre Computer (LoveRPi)** | Le Potato (AML-S905X-CC), Alta (AML-A311D 5 TOPS NPU) & Solitude drop-in Raspberry Pi 3B+/4B replacements | https://libre.computer/ |
| Companion SBCs | **LattePanda (DFRobot x86 SBCs)** | LattePanda Sigma (Intel Core i5-1340P), LattePanda Mu (N100 Compute Module) & 3 Delta x86 ROS 2 / Windows/Ubuntu SBCs | https://www.lattepanda.com/ |
| Companion SBCs | **AAEON (UP Bridge the Gap)** | UP Board, UP Squared Pro 7000 (Intel Alder Lake-N) & BOXER-8640AI compact NVIDIA Jetson Orin UAV computers | https://www.up-board.org/ |
| Companion SBCs | **Advantech (Industrial UAV Edge SBCs)** | MIC-711-OX / MIC-711-ON (Jetson Orin NX/Nano) & RSB-3720 2.5" Pico-ITX industrial drone companion boards | https://www.advantech.com/ |
| ESCs | **Hobbywing** | XRotor Pro 40A–80A VTOL ESCs, Platinum Pro 70A/80A BEC Fixed-Wing Pusher ESCs | https://www.hobbywing.com/ |
| ESCs | **T-Motor (ESCs)** | FLAME 60A/80A HV, ALPHA 40A/60A FOC Waterproof VTOL ESCs | https://store.tmotor.com/ |
| ESCs | **MicoAir Tech (ESCs)** | MicoAir 55A & 70A 4-in-1 AM32 / Bluejay Telemetry ESCs | https://micoair.com/en |
| ESCs | **Holybro (Tekko32 & DroneCAN ESCs)** | Tekko32 F4 45A/65A BLHeli_32 ESCs, Tekko32 Metal 65A & Kotleta20 DroneCAN ESCs | https://holybro.com/collections/escs |
| ESCs | **APD (Advanced Power Drives)** | 80F3x, 120F3x, HV Pro High-Voltage DroneCAN / Telemetry ESCs | https://powerdrives.net/ |
| Motors | **T-Motor** | MN4014 KV400, MN5008 KV340 Antigravity VTOL Lift Motors; AT3520 & AT4120 Fixed-Wing Pusher Motors | https://store.tmotor.com/ |
| Motors | **SunnySky USA / RC** | X4112S KV320/KV400, V4010 Heavy-Lift VTOL & X3520 Fixed-Wing Brushless Motors | https://sunnyskyusa.com/ |
| Motors | **Dualsky** | ECO 3520C, ECO 4120C, XM5050EA High-Efficiency Fixed-Wing Cruise Motors | http://www.dualsky.com/ |
| Motors | **KDE Direct** | KDE4012XF-400, KDE4215XF-465 Industrial Multi-Rotor & VTOL Brushless Motors | https://www.kdedirect.com/ |
| Propellers | **APC Propellers (Landing Products)** | 14×5.5MR, 15×5.5MR Multi-Rotor Lift Props; 13×8E, 14×8.5E Thin Electric Pusher Props | https://www.apcprop.com/ |
| Propellers | **Master Airscrew** | 13×8, 14×9 Electric Fixed-Wing & Multi-Rotor Composite Propellers | https://www.masterairscrew.com/ |
| Propellers | **HQProp** | 14×5, 15×5 Carbon-Reinforced Composite CW/CCW VTOL Propellers | https://www.hqprop.com/ |
| Propellers | **Mejzlik Propellers** | Aerospace-Grade Prepreg Carbon Fiber VTOL & Fixed-Wing Propellers (15"–22") | https://www.mejzlik.eu/ |
| Propellers | **XOAR International** | PJM-E Precision Pair Carbon & Laminated Beechwood Electric Propellers | https://www.xoarintl.com/ |
| Batteries | **Molicel (E-One Moli Energy)** | INR-21700-P45B (4500mAh 45A) & P50B High-Power Li-Ion Cells for 6S2P/8S2P VTOL Packs | https://www.molicel.com/ |
| Batteries | **Tattu / Gens Ace (Grepow)** | Tattu Plus 6S/12S Smart UAV LiPo & Semi-Solid High-Energy Density Packs (8000–16000mAh) | https://www.genstattu.com/ |
| Batteries | **Titan Power / Ampxell** | Pre-welded 6S2P & 6S3P Molicel P45B Long-Endurance Lithium-Ion UAV Battery Packs | https://www.gettitanpower.com/ |
| Sensors | **Holybro (Airspeed, Optical Flow & Rangefinders)** | Digital Differential Airspeed Sensor (MS4525DO Pitot), PMW3901 Optical Flow & ST VL53L1X ToF Rangefinder Modules | https://holybro.com/collections/sensors |
| Sensors | **Sensirion / Matek (Airspeed)** | SDP31 / SDP33 Digital Differential Pressure & MS4525DO Pitot Tube Airspeed Sensors | https://sensirion.com/ |
| Sensors | **LightWare LiDAR** | SF20/C, LW20/C Micro Laser Altimeters for Long-Range VTOL Terrain Following | https://lightwarelidar.com/ |
| GPS / GNSS | **MicoAir Tech (GNSS & RTK)** | MG-F10-A Dual-Frequency GNSS Module & MA-RTK-AIR-982 Dual-Antenna RTK Heading System | https://micoair.com/en |
| GPS / GNSS | **Holybro / u-blox (GNSS & H-RTK)** | DroneCAN H-RTK F9P Helical / Rover / Unicore UM982 Dual-Antenna, M9N & M10 High-Precision GNSS Compass Modules | https://holybro.com/collections/gps-rtk-systems |
| GPS / GNSS | **CUAV GNSS** | C-RTK 9Ps, Neo 3 Pro (u-blox M9N + RM3100 Industrial Anti-Interference Compass) | https://www.cuav.net/en/ |
| Telemetry Radios | **MicoAir Tech (Telemetry & Wi-Fi 6 Links)** | MicoAir-WiFi-Link Dual-Band Wi-Fi 6, LR900 (900MHz), LR24 (2.4GHz), TRS 2-in-1 RC & Telemetry, MSTAR24 Swarm Mesh | https://micoair.com/en |
| Telemetry Radios | **Holybro (SiK, P900 & XBP9X Telemetry)** | SiK Telemetry Radio V3 (100mW/500mW 915/433MHz), Microhard P900 & Digi XBee XBP9X Enclosed UAV Radios | https://holybro.com/collections/telemetry-radios |
| Telemetry Radios | **RFDesign (RFD900x / RFD868x)** | RFD900x-US & RFD868x-EU 1W (+30dBm) Long-Range 40km+ AES-Encrypted MAVLink Telemetry Modems | https://rfdesign.com.au/ |
| Telemetry Radios | **Microhard Systems** | pMDDL2450, n920X & p900 Industrial MIMO IP / Serial BVLOS Drone Command & Telemetry Radios | https://www.microhardcorp.com/ |
| Telemetry Radios | **Silvus Technologies** | StreamCaster SC4200E & SC4400E Tactical MN-MIMO Mesh Video & C2 Data Links | https://silvustechnologies.com/ |
| FPV Systems | **DJI (Digital FPV Air Units)** | DJI O4 Air Unit Pro / O3 Air Unit (1080p/120fps, 4K onboard recording) & DJI Goggles 3 / Integra | https://www.dji.com/ |
| FPV Systems | **CaddxFPV / Walksnail Avatar HD** | Walksnail Avatar HD Pro Kit (Sony Starvis II Night Sensor), Moonlight 4K, Goggles X & Analog Ratel 2 | https://caddxfpv.com/ |
| FPV Systems | **HDZero (Divimath)** | HDZero Freestyle V2 VTX, Whoop Lite, Event VRX & Ultra-Low Fixed-Latency Digital HD FPV Goggles | https://www.hd-zero.com/ |
| FPV Systems | **RushFPV** | Rush Tank Max Solo (2.5W 5.8GHz), RushFPV 1.3GHz/3.3GHz Long-Range VTXs & TrueRC / Cherry Antennas | https://www.rushfpv.net/ |
| FPV Systems | **Foxeer** | Foxeer Reaper Extreme 2.5W VTX, Wildfire Receiver, Lollipop 4+ Antennas & Low-Latency FPV Cameras | https://www.foxeer.com/ |
| RC Transmitters & Receivers | **RadioMaster RC (EdgeTX & ExpressLRS)** | TX16S Mark II Max, Boxer Crush, GX12 Dual-Band Gemini Xrossband Transmitters & RP3/RP4TD Diversity ELRS Receivers | https://www.radiomasterrc.com/ |
| RC Transmitters & Receivers | **RadioLink Electronic** | RadioLink T16D & AT9S Pro Transmitters; R16F / R12DS SBUS/CRSF/PWM Long-Range FHSS Receivers | https://www.radiolink.com/ |
| RC Transmitters & Receivers | **Team BlackSheep (TBS Crossfire / Tracer)** | TBS Crossfire TX/Nano Diversity RX (868/915MHz 40km+ CRSF Link), TBS Tango 2 & Mambo Transmitters | https://www.team-blacksheep.com/ |
| RC Transmitters & Receivers | **FrSky Electronic** | TANDEM X20 PRO AW (Dual-Band 900MHz + 2.4GHz), Twin X14 & TD R18 / R10 Redundant SBUS/FBUS Receivers | https://www.frsky-rc.com/ |
| RC Transmitters & Receivers | **SIYI Technology (Handheld GCS & Links)** | SIYI UniRC 7 & MK32 / MK15 Enterprise Handheld Ground Control Stations (Integrated FHD Screen + Video + MAVLink + RC) | https://siyi.biz/en/ |
| RC Transmitters & Receivers | **CubePilot Herelink** | Herelink v1.1 All-in-One Digital HD Video, MAVLink Telemetry & Touch-Screen Handheld Remote Controller for PX4/QGC | https://www.cubepilot.com/#/herelink/overview |
| RC Transmitters & Receivers | **FlySky RC** | FS-ST16, Paladin PL18 EV & FS-i6X Transmitters; FS-iA10B / FTr10 PPM/i-BUS/SBUS Receivers | https://www.flysky-cn.com/ |
| RC Transmitters & Receivers | **Spektrum RC (Horizon Hobby)** | iX20, NX10+, DX6i DSMX Transmitters, AR8020T / AR10360T SRXL2 Telemetry Receivers & WS2000 Sim Dongle | https://www.spektrumrc.com/ |
| Servos & Actuators | **KST Digital Servos** | KST X10, X10 Mini, A12-T, X15-1808 Full-CNC Aluminum Case Steel-Gear High-Voltage Wing & Tail Servos | https://www.kstsz.com/ |
| Servos & Actuators | **Hitec RCD / Hitec Commercial Solutions** | D85MG, HS-5087MH, MD950TW & Industrial CAN/UAVCAN Brushless Actuators with Position Feedback | https://hitecrcd.com/ |
| Servos & Actuators | **Savöx Servos** | SV-1250MG, SV-1261MG, SW-1250MG Waterproof Coreless/Brushless High-Voltage Metal-Gear UAV Servos | https://www.savoxusa.com/ |
| Servos & Actuators | **MKS Servos** | MKS HV6130, HBL6625, HV747R Aerospace-Grade Titanium/Steel-Gear Thin-Wing & Tail Actuators | https://www.mks-servo.com.tw/ |
| Servos & Actuators | **Volz Servos (Aerospace Actuators)** | DA 15-N, DA 22 & DA 26 Redundant RS-485 / DroneCAN Submersible Certified UAV Actuators | https://www.volz-servos.com/ |
| Servos & Actuators | **EMAX Model** | ES08MD II, ES3054 & ES3352 Budget Metal-Gear Digital Mini Servos for Lightweight Foam/LW-PLA Prototypes | https://emaxmodel.com/ |
| LiDAR Scanners | **Livox (3D Mapping LiDAR)** | Livox Mid-360 (360° 3D SLAM/Obstacle Avoidance, 265g) & Avia Long-Range Aerial Survey LiDAR | https://www.livoxtech.com/ |
| LiDAR Scanners | **Ouster / Velodyne LiDAR** | Ouster OS0 / OS1-64 / OS1-128 & Velodyne Puck LITE Ultra-Light 3D Aerial Mapping LiDARs | https://ouster.com/ |
| LiDAR Scanners | **Hesai Technology** | Hesai XT32 / XT16 & PandarXTM Lightweight High-Precision UAV Survey & Corridor Mapping LiDARs | https://www.hesaitech.com/ |
| LiDAR Scanners | **Benewake LiDAR** | TFmini-S, TF-Luna, TF02-Pro (40m IP65) & TF03 (180m) Single-Point UART/I2C/CAN Terrain-Following Altimeters | https://en.benewake.com/ |
| LiDAR Scanners | **YellowScan / GreenValley International** | Turnkey Surveyor Ultra, Mapper+ & LiAir X3/X4 Integrated GNSS-INS UAV LiDAR Payloads | https://www.yellowscan.com/ |
| Cameras & Gimbals | **Teledyne FLIR (Thermal IR & Radiometric)** | FLIR Boson+, Hadron 640R (Dual 640×512 Thermal IR + 64MP EO RGB) & Vue TZ20-R UAV Thermal Cameras | https://www.flir.com/suas/ |
| Cameras & Gimbals | **RunCam (Night Starlight, B/W & Color)** | Night Eagle 3 Pro (Ultra-Low-Light 11390mV/Lux-sec B/W Monochrome Night Camera), Phoenix 2 Color & Split 4K | https://shop.runcam.com/ |
| Cameras & Gimbals | **Sony Semiconductor / Alpha Drone Payloads** | Sony ILX-LR1 (61MP Full-Frame UAV Photogrammetry Camera), IMX296/IMX264 Global-Shutter B/W & Color VIO Sensors | https://pro.sony/ |
| Cameras & Gimbals | **SIYI Technology (EO/IR Gimbals)** | ZT30 (Quad-Sensor 4K 30× Optical Zoom + 640 Thermal + Laser Rangefinder), ZT6, A8 Mini & ZR10 3-Axis Gimbals | https://siyi.biz/en/ |
| Cameras & Gimbals | **Gremsy (Industrial MAVLink Gimbals)** | Vio F1 (EO/IR + LRF Zoom Payload), Pixy U, T3V3 & Mio MAVLink/PX4 Quick-Release Camera Gimbals | https://gremsy.com/ |
| Cameras & Gimbals | **NextVision Stabilized Systems** | NightHawk2-UZ, DragonEye2 & Raptor Micro-Stabilized Long-Range Day EO / Cooled & Uncooled Thermal IR Gimbals | https://www.nextvision-sys.com/ |
| Cameras & Gimbals | **InfiRay / NocPix (Thermal Cores)** | Micro III 384/640 & Mini2 256/384 (20g Ultra-Light Uncooled VOx LWIR Thermal Camera Cores for VTOLs) | https://www.infiray.com/ |
| Cameras & Gimbals | **Viewpro UAV Gimbals** | Q30T Pro, U30TIR & Z40K Dual/Triple-Sensor Optical Zoom + Thermal Tracking + Laser Rangefinder Gimbals | https://www.viewprouav.com/ |
| Cameras & Gimbals | **ids / Basler / Arducam (B/W & Global Shutter)** | OV9281 / OG02B10 Monochrome B/W Global-Shutter MIPI/USB3 Cameras for VIO, AprilTag Landing & Machine Vision | https://www.arducam.com/ |
| Drone Kits & Airframes | **Holybro (PX4 Development Drone Kits)** | PX4 Vision Autonomy Dev Kit, X500 V2 ARF/PNP Carbon Fiber Quad Kit, S500 V2 & QAV250 Complete PX4/ArduPilot Drone Kits | https://holybro.com/collections/multicopter-kit |
| Drone Kits & Airframes | **Foxtech FPV / Foxtech UAV** | Babyshark 260, Ayers, Nimbus VTOL, Great Shark 330 & Rhea 160 Composite Kevlar/Carbon QuadPlane Airframe Kits | https://www.foxtechfpv.com/ |
| Drone Kits & Airframes | **Yangda Security / UAV** | Skywhale, YD-A22 & Walker-2400 Heavy-Lift Carbon-Fiber Lift-and-Cruise Fixed-Wing VTOL Kits | https://www.yangdaonline.com/ |
| Drone Kits & Airframes | **HeeWing RC / Ranger Series** | HeeWing T1 Ranger VTOL, T2 Cruza & F-01 Compact Modular Tilt-Rotor / QuadPlane PNP Kits | https://www.heewing.com/ |
| Drone Kits & Airframes | **VolantexRC / Phoenix / Ranger** | Ranger 2000, Ranger 2400 & Phoenix 2400 EPO Airframe Kits for QuadPlane Conversion & SITL Validation | https://www.volantexrc.com/ |
| Drone Kits & Airframes | **Titan Dynamics / Eclipson 3D** | 3D-Printable LW-PLA Fixed-Wing & VTOL Reference Airframe STL Designs (Falcon, Sovereign, Model Z) | https://www.titandynamics.org/ |
| Power, Wiring & Connectors | **Holybro (Power Modules, PDBs & JST-GH Wiring)** | PM02D / PM03D Digital I2C Power Modules, PM06 / PM07 High-Current PDBs, DroneCAN Power Modules & Pixhawk JST-GH Cable Kits | https://holybro.com/collections/power-modules-pdbs |
| Power, Wiring & Connectors | **Amass Electronics (High-Current Connectors)** | XT60PW, XT90-S (Anti-Spark), AS150U, MR30/MT60 (3-Phase Motor Boom Plugs) & XT30 Gold-Plated Connectors | http://www.china-amass.com/ |
| Power, Wiring & Connectors | **Mauch Electronic (Hall-Effect Power Modules)** | Mauch HS-200-HV (200A 4S–14S Hall Sensor), PL-Sensor & Dual BEC Redundant Power Supplies for Pixhawk/Cube | https://www.mauch-electronic.com/ |
| Power, Wiring & Connectors | **JST / Molex (Drone Standard Harnesses)** | JST-GH 1.25mm Positive-Lock Pixhawk Standard Connectors (4/6/8/10-Pin) & Molex Clik-Mate 2.0mm DroneCAN Plugs | https://www.jst.com/ |
| Power, Wiring & Connectors | **Alpha Wire / BNTECHGO (Silicone Wire)** | Ultra-Flexible 200°C Tinned-Copper Silicone Wire (8/10/12/14/16 AWG Power & 22/26 AWG Twisted Servo/CAN) | https://www.alphawire.com/ |
| Power, Wiring & Connectors | **Castle Creations (High-Output BECs)** | CC BEC 2.0 Waterproof (14A Peak, 4.75V–12V Adjustable) & CC BEC Pro 20A for High-Torque VTOL Wing Servos | https://www.castlecreations.com/ |
| Power, Wiring & Connectors | **Lemo / Fischer Connectors** | IP68 Push-Pull Circular Quick-Disconnect Wing-to-Fuselage & External Payload Pod Harnesses | https://www.lemo.com/ |
| Parachute & Safety Recovery | **ParaZero Drone Safety Systems** | SafeAir Pyrotechnic & Mechanical Autonomous Ballistic Parachute Recovery Systems (ASTM F3322 Operations Over People) | https://parazero.com/ |
| Parachute & Safety Recovery | **Mars Parachutes / Fruity Chutes** | Iris Ultra Compact Annular & Cruciform UAV Recovery Parachutes, CO2 / Spring Canister Ejectors & Auto-Triggers (2–50kg MTOW) | https://fruitychutes.com/ |
| Parachute & Safety Recovery | **Galaxy GRS (Ballistic Rescue Systems)** | Galaxy GRS Fast-Opening Ballistic Parachutes for Heavy Fixed-Wing VTOLs & Unmanned Cargo Aircraft | https://www.galaxy-rs.cz/ |
| Parachute & Safety Recovery | **AVSS (Aerial Vehicle Safety Solutions)** | PRS-M300 / PRS-M350 ASTM-Compliant Parachute Recovery & Flight Termination Systems (FTS) | https://www.avss.co/ |
| Airborne Generators & Hybrid Power | **Currawong Engineering** | Corvid-29 / Corvid-50 Electronic Fuel Injection (EFI) 2-Stroke UAV Engines & Integrated Starter-Alternators | https://currawong.aero/ |
| Airborne Generators & Hybrid Power | **Intelligent Energy (Hydrogen UAV Fuel Cells)** | IE-SOAR 800W–2.4kW Lightweight Proton Exchange Membrane (PEM) Hydrogen Fuel Cell Power Modules for Multi-Hour VTOLs | https://www.intelligent-energy.com/ |
| Airborne Generators & Hybrid Power | **Pegasus Aeronautics / SkyPower** | GE-70 & SP-55 FI Series Hybrid-Electric Range Extender Generators (2kW–5kW) for Heavy-Lift QuadPlanes | https://pegasusaero.ca/ |
| Airborne Generators & Hybrid Power | **HFE International (UAV Heavy Fuel & EFI)** | GenPod & Heavy-Fuel (JP-8 / Jet-A) EFI Propulsion and Onboard Generator Systems for Long-Range VTOLs | https://www.hfeinternational.com/ |
| GCS Hardware & Antennas | **uAvionix (ADS-B, Remote ID & C2)** | pingRX Pro, ping200X Mode S/ADS-B Transponders, truFYX SBAS GPS & pingRID NDAA Remote ID Modules | https://uavionix.com/ |
| GCS Hardware & Antennas | **TrueRC Canada / VAS (Video Antenna Systems)** | X-Air, Singularity, Matchstick & Crosshair Circularly Polarized High-Gain Directional & Omni UAV Antennas | https://www.truerc.ca/ |
| GCS Hardware & Antennas | **Panorama Antennas / Southwest Antennas** | Ruggedized MIMO Directional Sector, Omni & Tracking Base-Station Antennas (900MHz / L-Band / S-Band / C-Band) | https://www.southwestantennas.com/ |
| GCS Hardware & Antennas | **Getac / Panasonic Toughbook** | Sunlight-Readable MIL-STD-810H IP66 Rugged Field Tablets & Laptops for QGroundControl & Mission Planner GCS | https://www.getac.com/ |
| Carbon Tubes, Filaments & Release Winches | **RockWest Composites / DragonPlate** | Roll-Wrapped 3K Twill Carbon Fiber Main Spar & Boom Tubes (Ø16–25mm), Pultruded Strips & CNC Gussets | https://www.rockwestcomposites.com/ |
| Carbon Tubes, Filaments & Release Winches | **ColorFabb / Polymaker / Bambu (3D Aero Filaments)** | ColorFabb LW-PLA & LW-ASA (Active Foaming Wing Skins), Polymaker Polylite LW-PLA, PA6-CF & PETG-CF Structural Filaments | https://colorfabb.com/ |
| Carbon Tubes, Filaments & Release Winches | **Zubax Robotics (Electro-Permanent Magnets)** | FluxGrip FG40 / NicaDrone EPM688 Electro-Permanent Magnetic Cargo Release Latches (Zero Steady-State Power Draw) | https://zubax.com/ |
| Carbon Tubes, Filaments & Release Winches | **A2Z Drone Delivery (Tethered Delivery Winches)** | RDS2 & RDSX Commercial Autonomous UAV Delivery Winches with Auto-Release Hook & Anti-Pendulum Control | https://www.a2zdronedelivery.com/ |