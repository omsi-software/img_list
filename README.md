# System images

<details>
<summary>SPRING7-10</summary>
                     
[Buildroot](https://drive.omsi-group.com/index.php/s/iRRJ7wmPrwcffmQ)\
[Android](https://drive.omsi-group.com/index.php/s/t37DSepTfAkAasb)

</details>
  
<details>
<summary>Apollo7-10 pro</summary>
  
[Buildroot](https://drive.omsi-group.com/index.php/s/fjZgGNWRCeBXpQj)\
[Android](https://drive.omsi-group.com/index.php/s/CzAmyatAHzLX4RS)

</details>

<details>
<summary>ApolloX</summary>
  
[Android](https://drive.omsi-group.com/index.php/s/nPzz9s6SpL9fbYC)

</details>
  
<details>
<summary>Apollo7 gen2</summary>
  
[Buildroot](https://drive.omsi-group.com/index.php/s/wSgMDgc4iskZQCn)\
[Android](https://drive.omsi-group.com/index.php/s/iBNoTaNxz5aq2my)\
[Android MIX](https://drive.omsi-group.com/index.php/s/JkdRaaB46srwQ7k) <sup>[↩](#migration-flow)</sup>\
[Debian](https://drive.omsi-group.com/index.php/s/5MayfRmARJRMmNc)

</details>
  
<details>
<summary>Apollo12 gen2</summary>
  
[Buildroot](https://drive.omsi-group.com/index.php/s/JD3M9zYbTKnjnE5)\
[Android](https://drive.omsi-group.com/index.php/s/fKNxGXi8Zd5zxZW)\
[Android MIX](https://drive.omsi-group.com/index.php/s/JkdRaaB46srwQ7k)<sup>[↩](#migration-flow)</sup>\
[Debian](https://drive.omsi-group.com/index.php/s/MinemLsrSP58FWr)

</details>
  
<details>
<summary>Apollo12 gen2 pro</summary>
  
[Android](https://drive.omsi-group.com/index.php/s/2P3MYoJeSTj3GPe)\
[Debian](https://drive.omsi-group.com/index.php/s/4G5jywqfD7ciD7J)\
[Debian A+B](https://drive.omsi-group.com/index.php/s/WLRo9HZ77E7BmYk) > Only works with min 32GB EMMC 

</details>

  
<details>
<summary>Apollo12 gen2 plus</summary>
  
Android:        [Android](https://drive.omsi-group.com/index.php/s/9ZNBwWdQFBosTN6)\
Debian:         [Debian](https://drive.omsi-group.com/index.php/s/LWcnj3FrdqA9KXs)

</details>
  
<details>
<summary>SPRING10 gen2 pro</summary>
  
[Buildroot](https://drive.omsi-group.com/index.php/s/ZBL2cq63GdsQKmo)\
[Android](https://drive.omsi-group.com/index.php/s/cneBEr7d5DtMnqc)\
[Android MIX](https://drive.omsi-group.com/index.php/s/BQx24Cxk4ASR7jc)<sup>[↩](#migration-flow)</sup>\
[Debian](https://drive.omsi-group.com/index.php/s/t6epNPHs6iDKGZj)

</details>
  
<details>
<summary>SPRING10 gen2 plus</summary>
  
[Buildroot](https://drive.omsi-group.com/index.php/s/NXnEfamJJqCmAZm)\
[Android](https://drive.omsi-group.com/index.php/s/sbCNWw5szGG7Gz5)\
[Android MIX](https://drive.omsi-group.com/index.php/s/BQx24Cxk4ASR7jc)<sup>[↩](#migration-flow)</sup>\
[Debian](https://drive.omsi-group.com/index.php/s/L2AeRkXyZHebYyE)

</details>

[^2]: See below for installation instructions


------------





<details>
<summary> Android MIX details </summary>
# MIX versions: Firmware Merging Solution for Multiple Device Models

  
## Objective
Unify Android firmware across multiple device models to:
- Accelerate firmware iteration
- Simplify maintenance and updates
- Reduce version fragmentation

---

## Concept Overview
A **MIX Firmware** allows multiple hardware models to share a single firmware package.  
Model-specific behavior is dynamically configured through **eeprom_config.json**.

---

## Firmware Identification
| Model | Transitional Firmware | MIX Version |
|--------|----------------------|--------------|
| **Apollo Gen2 (7")** | `CP_APOLLO2_A_DEV-2DF077A6_LCD7_B1_MDM_20250321.img` | Apollo Gen2 MIX |
| **Apollo Gen2 (12")** | `CP_APOLLO2_A_DEV-2DF077A6_LCD12_B0_MDM_20250321.img` | Apollo Gen2 MIX |
| **Spring Gen2 Pro** | `CP_SP2-10PRO_A_CE1DF806_LCD10_B0_CN_MDM_20250114.img` | Spring Gen2 10 MIX |
| **Spring Gen2 Plus** | `CP_SP2-10PLUS_A_61FA77E2_LCD10_B0_EU_MDM_20250114_OTA.zip` | Spring Gen2 10 MIX |

Transitional firmwares can be found [here](https://drive.omsi-group.com/index.php/s/wXzkqji6zQDzexG).
---

## Migration Flow

```plaintext
┌────────────────────────────┐
│ Step 1: Transitional Firmware │
│ - Flash model-specific firmware  │
│ - Updates EEPROM with model ID   │
│   (e.g., persist.hw.Screen1For=APOLLO2-7) │
└───────────────┬────────────────┘
                │
                ▼
┌────────────────────────────┐
│ Step 2: MIX Firmware Installation │
│ - Flash any MIX version firmware   │
│ - System reads EEPROM model ID     │
│ - Adapts configuration automatically │
└────────────────────────────┘
```

---

## Notes
- Transitional firmware is **only needed once** per device to update EEPROM.
- Alternatively, EEPROM can be **manually configured** to skip transitional flashing.
- Older devices remain compatible; adding new model identifiers is backward-safe.

---

## Key Benefit
> One unified MIX firmware image supports multiple device models through dynamic configuration, reducing engineering overhead and improving firmware release agility.

  
<details>



