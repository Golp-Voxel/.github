<div align="center">

# Golp-Voxel

**Tango Control System device servers for experimental physics instrumentation**

[![VOXEL Group — IPFN, IST](https://img.shields.io/badge/VOXEL%20Group-IPFN%20%7C%20IST-blue?style=for-the-badge)](https://www.ipfn.tecnico.ulisboa.pt/voxel)
[![Tango Controls](https://img.shields.io/badge/Tango%20Controls-device%20servers-orange?style=for-the-badge)](https://www.tango-controls.org/)
[![Python](https://img.shields.io/badge/Python-PyTango-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://pytango.readthedocs.io/)

</div>

Each repository is an independent Python device server (PyTango) that exposes a physical instrument to the Tango ecosystem, enabling remote control, logging, and integration with experiment automation.

> **New to Tango?** See [**HowTo**](https://github.com/Golp-Voxel/HowTo) for installation guides, device server setup steps, and experiment examples.

---

## 📷 Cameras

| Repository | Instrument | Library | Notes |
|:---|:---|:---:|:---|
| [Tango-Basler_AG_Camera](https://github.com/Golp-Voxel/Tango-Basler_AG_Camera) | Basler AG cameras | pypylon | Snap, continuous acquisition, ROI, auto-exposure/gain |
| [Tango-IDS_Camera](https://github.com/Golp-Voxel/Tango-IDS_Camera) | IDS cameras | ids_peak | Software trigger, USB 3 required |
| [Tango_GreatEyesCCD](https://github.com/Golp-Voxel/Tango_GreatEyesCCD) | GreatEyes CCD | greateyes.dll | Full-frame acquisition, Peltier temperature control |
| [Tango-MiniPIX_TPX3](https://github.com/Golp-Voxel/Tango-MiniPIX_TPX3) | MiniPIX TPX3 particle detector | PixetAPI / pypixet | Python 3.7 required |

## 🔩 Motion Controllers

| Repository | Instrument | Library | Notes |
|:---|:---|:---:|:---|
| [Tango_Standa](https://github.com/Golp-Voxel/Tango-Standa_8SMC5-USB) | Standa 8SMC5-USB multi-axis controller | libximc | Multiple motors, virtual device support |
| [Tango-Newport_AG_UC8](https://github.com/Golp-Voxel/Tango-Newport_AG_UC8) | Newport AG-UC8 piezo controller | qcodes_contrib_drivers | 4 channels, step amplitude, position measurement |
| [Tango_SMC100](https://github.com/Golp-Voxel/Tango_SMC100) | Newport SMC100 single-axis controller | pyserial | Absolute/relative moves, home search, status codes |

## 🔬 Other Instruments

| Repository | Instrument | Library | Notes |
|:---|:---|:---:|:---|
| [Tango-Arduino_Shutter](https://github.com/Golp-Voxel/Tango-Arduino_Shutter) | Thorlabs shutter via Arduino | pyserial | JSON serial protocol, open/close cycles; PlatformIO firmware included |
| [Tango-DppMCA](https://github.com/Golp-Voxel/Tango-DppMCA) | Amptek DppMCA X-ray spectrometer | pyusb | Up to 8000-channel spectrum via USB |
| [Tango_Thorlabs](https://github.com/Golp-Voxel/Tango_Thorlabs) | Thorlabs instruments | Thorlabs TSI SDK | |
| [Tango_SLM](https://github.com/Golp-Voxel/Tango_SLM) | Spatial Light Modulator | — | |

## 🚧 In Development

| Repository | Instrument | Status |
|:---|:---|:---|
| [Tango-Thorlabs_DMP40](https://github.com/Golp-Voxel/Tango-Thorlabs_DMP40) | Thorlabs DMP40 deformable mirror | ctypes prototype ready; Tango wrapper in progress |
| [Tango-EdwardsController_6-Gauge](https://github.com/Golp-Voxel/Tango-EdwardsController_6-Gauge) | Edwards TIC vacuum gauge controller | Serial communication tested; Tango wrapper in progress |

## 🛠️ Utilities

| Repository | Description |
|:---|:---|
| [HowTo](https://github.com/Golp-Voxel/HowTo) | Tango installation guide, device server setup steps, and experiment examples |
| [VideoStreamTool](https://github.com/Golp-Voxel/VideoStreamTool) | Flask MJPEG live video streaming from any Tango camera device server |

---

## Getting Started

All device servers follow the same setup pattern:

```bash
git clone https://github.com/Golp-Voxel/<repo>.git
python -m venv tango-env
tango-env\Scripts\activate
pip install -r Requirements.txt
```

Copy `<DeviceName>.bat.temp` → `<DeviceName>.bat`, update the paths, then register the device in the Tango Database using **Jive/Astor**. See [HowTo](https://github.com/Golp-Voxel/HowTo) for the full step-by-step guide.
