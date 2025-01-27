[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/O5O119O0KM) 
# MVSep-MDX23 Colab Fork v2.5

Adaptation of MVSep-MDX23 algorithm for Google Colab, with a few tweaks:

**Colab Notebook:**  
[**MVSep-MDX23-Colab_v2.5**](https://colab.research.google.com/github/jarredou/MVSEP-MDX23-Colab_v2/blob/v2.5/MVSep-MDX23-Colab.ipynb)  
<br>

### Recent changes:

**v2.5.2** *(27 JAN 2025)*  
- **Custom drum model** added to further split the **drums** stem into **kick** and **hihat**. This is especially helpful for **VirtualDJ**, which can use a 5-stem layout (vocals, bass, kick, hihat, other).  
- The custom model by [inagoy](https://github.com/inagoy/drumsep) is automatically used if the file `modelo_final.th` is found in the `models/` folder.  
- Adjusted `inference.py` to detect and apply the custom separation step after the main 4-stem separation is complete.  

**v2.5.1** *(24 SEPT 2024)*  
- Improved memory management (use `--large_gpu` to keep all models in GPU during folder batch processing).  

**v2.5** *(13 AUG 2024)*  
- **Kim's MelBand-Roformer model** added.  

**v2.4** *(7 APR 2024)*  
- **BS-Roformer** models from `viperx` added.  
- **MDX-InstHQ4** model added (optional).  
- FLAC output supported.  
- Input volume gain control.  
- Option to filter vocals below 50 Hz.  
- Improved chunking algorithm (fewer clicks).  
- Code cleanup.

<details>
  <summary>Full changelog:</summary>
  <br>
  <font size=2>
  
  [**v2.3**](https://github.com/jarredou/MVSEP-MDX23-Colab_v2/tree/v2.3)  
  - HQ3-Instr model replaced by VitLarge23 (thanks to MVSep).  
  - Improved MDXv2 processing (thanks to Anjok).  
  - Improved BigShifts algo (v2).  
  - BigShifts processing added to MDXv3 & VitLarge.  
  - Faster folder batch processing.

  [**v2.2.2**](https://github.com/jarredou/MVSEP-MDX23-Colab_v2/tree/v2.2)  
  - Improved MDXv3 chunking code (thanks to HymnStudio).  
  - D1581 demo model replaced by new InstVocHQ MDXv3 model.

  **v2.2.1**  
  - Added custom weights feature.  
  - Multiple bug fixes.  
  - File or folder input support.

  **v2.2**  
  - Added MDXv3 compatibility.  
  - Added MDXv3 demo model D1581 in vocals stem multiband ensemble.  
  - Added VOC-FT Fullband SRS (replaces UVR-MDX-Instr-HQ3).  
  - 2-stems feature: output only vocals/instrumental (faster).  
  - 16-bit output option.  
  - “BigShift trick” for MDX models.  
  - Independent overlap values for MDX, MDXv3, Demucs.  
  - Volume compensation fine-tuning for MDX-VOC-FT.

  [**v2.1 (by deton24)**](https://github.com/deton24/MVSEP-MDX23-Colab_v2.1)  
  - Updated with MDX-VOC-FT instead of Kim Vocal 2.

  [**v2.0**](https://github.com/jarredou/MVSEP-MDX23-Colab_v2/tree/2.0)  
  - Updated with new Kim Vocal 2 & UVR-MDX-Instr-HQ3 models.  
  - Folder batch processing.  
  - Fixed high frequency bleed in vocals.  
  - Fixed volume compensation for MDX models.

  </font>
</details>

### Usage

1. **Clone/Fork** this repository or open the [Colab Notebook](https://colab.research.google.com/github/jarredou/MVSEP-MDX23-Colab_v2/blob/v2.5/MVSep-MDX23-Colab.ipynb).
2. **Install Dependencies** (in Colab, automatically handled by the provided script).
3. **(Optional)** Upload or place custom models in the `models/` folder.
   - For example, the new **custom drum model** must be named `modelo_final.th` and placed in `models/` to enable the automatic “kick” + “hihat” separation.
4. **Run the separation** using the provided scripts or the interactive Colab cells.

### About the Custom Drum Model

- Developed by [inagoy](https://github.com/inagoy/drumsep).  
- Automatically splits the "drums" stem into two additional stems:  
  - **kick** (everything except hihat-like content)  
  - **hihat** (labelled as “platillos” in the model’s sources)  
- If the file `modelo_final.th` is present, the script attempts to load it after the main separation.  
- Useful for **VirtualDJ** or similar DJ software that uses 5-stem separation (vocals, bass, kick, hihat, and other).

### Credits

- [ZFTurbo/MVSep](https://github.com/ZFTurbo/MVSEP-MDX23-music-separation-model)  
- Models by [Demucs](https://github.com/facebookresearch/demucs), [Anjok](https://github.com/Anjok07/ultimatevocalremovergui), [Kimberley Jensen](https://github.com/KimberleyJensen), [aufr33](https://github.com/aufr33), and **viperx**  
- Additional drum model by [inagoy](https://github.com/inagoy/drumsep)  
- Adaptation & tweaks by [jarredou](https://github.com/jarredou/MVSEP-MDX23-Colab_v2/)  

<br>  
Enjoy the new 5-stem separation experience!  
If you find this project useful, please consider supporting via [Ko-fi](https://ko-fi.com/O5O119O0KM).  