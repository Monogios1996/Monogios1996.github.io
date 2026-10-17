---
title: Unit 10 — Deep Learning in Action: NVIDIA DLSS
permalink: /modules/intelligent-agents/evidence/artefacts/unit-10-deep-learning-in-action-dlss/
---

# Unit 10 — Deep Learning in Action

**Activity:** Research an application of Deep Learning that is likely to have an impact on society, covering an overview of the technology, how it works, and relevant ethical, privacy, social-good or other socio-technical impacts.

**Type:** Individual learning activity  
**Status:** Completed

## Submitted Answer

### NVIDIA DLSS: Deep Learning in Gaming and Its Social Implications

NVIDIA’s Deep Learning Super Sampling (DLSS) is an application of deep learning that improves graphics performance in video games. Its Super Resolution feature reconstructs higher-resolution images from lower-resolution inputs, reducing the amount of conventional rendering required. Separate Frame Generation features create additional frames to improve visual smoothness. I consider DLSS socially relevant because it can influence access to demanding games, hardware purchasing decisions and expectations about graphics performance.

**How the technology works**

DLSS uses a trained neural network rather than simply enlarging an image. NVIDIA’s explanation of DLSS 2.0 describes training against high-quality reference images. During gameplay, the model combines lower-resolution images, motion information and information from previous frames to reconstruct the output. The trained network runs on specialised processing units called Tensor Cores within compatible RTX graphics cards (NVIDIA, 2020).

The technology has subsequently developed further. DLSS 4 introduced transformer-based models for Super Resolution and Ray Reconstruction. These models capture relationships across image regions and frames, helping preserve detail and reduce visual artefacts. Frame Generation performs a different task: estimating intermediate frames between conventionally rendered ones (NVIDIA, 2025).

**Potential social and ethical impacts**

One potential benefit is making demanding games more playable on existing compatible hardware. This could allow some players to postpone upgrades and continue participating in gaming communities. However, access is uneven. NVIDIA’s compatibility information shows that Super Resolution supports several RTX generations, while some frame-generation features require newer hardware (NVIDIA, n.d.). This raises questions about affordability and dependence on a particular manufacturer’s ecosystem.

Consumer transparency is another concern. Generated frames increase the displayed frame rate, but that figure alone does not establish how quickly a game responds to player input. NVIDIA’s research treats smoothness, image quality and latency as distinct considerations (NVIDIA, 2025). I would therefore argue that performance comparisons should disclose whether frame generation is enabled and report responsiveness alongside frame rates. Otherwise, consumers may interpret a larger number as an equivalent improvement in every aspect of gameplay.

Environmental benefits should also be treated as possibilities rather than established outcomes. Rendering fewer pixels could reduce energy requirements at a fixed performance target, but neural processing also consumes energy, and players may use the performance gains to increase graphical settings. Establishing a net benefit would require measurements under comparable conditions.

Overall, I regard DLSS as a useful application of deep learning whose value extends beyond visual quality. Responsible adoption requires clear performance reporting, consideration of hardware accessibility and evidence to support environmental claims.

**References**

NVIDIA (2020) *NVIDIA DLSS 2.0: A big leap in AI rendering*. Available at: https://www.nvidia.com/en-gb/geforce/news/nvidia-dlss-2-0-a-big-leap-in-ai-rendering/ (Accessed: 17 October 2026).

NVIDIA (2025) *DLSS 4: Transforming real-time graphics with AI*. Available at: https://research.nvidia.com/labs/adlr/DLSS4/ (Accessed: 17 October 2026).

NVIDIA (n.d.) *DLSS technology*. Available at: https://www.nvidia.com/en-us/geforce/technologies/dlss/ (Accessed: 17 October 2026).

---

## Portfolio note

This activity demonstrates the application of deep-learning concepts to a real-world technology and extends the technical analysis into socio-technical evaluation. The discussion considers not only how DLSS works, but also consumer transparency, hardware accessibility, vendor dependence and the limits of environmental claims.

It provides **supporting evidence for LO3** through consideration of social, ethical and professional implications of AI technology. It is not presented as evidence of implementing an agent-based system.
