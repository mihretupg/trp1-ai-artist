# TRP-1 Challenge-2 Submission Report

By: Miihretu Petros
Date: 2/2/2026
 

## Environment Setup Documentation

**APIs Configured:**

* Google Gemini (Lyria music, Veo video, Imagen images)
* AIMLAPI (MiniMax music with vocals)

**Issues Encountered:**

* `uv` command not recognized on Windows
* Veo video generation failed (SDK mismatch)
* KlingAI authentication unavailable

**Resolutions / Workarounds:**

* Used `python -m uv` instead of `uv`
* Focused on audio generation instead of Veo video
* Skipped KlingAI provider

---

## Codebase Understanding

**Architecture Description:**

* `src/ai_content/` contains main modules for content generation
* `providers/` handles API integration for each provider
* `pipelines/` orchestrates CLI arguments, provider selection, prompt execution, and output handling

**Key Insights:**

* Modular provider system allows easy addition of new APIs
* Preset system simplifies repeated content generation
* CLI abstraction enables consistent user interface across providers

**Pipeline Orchestration:**

* Parse CLI arguments
* Load chosen provider
* Configure generation based on style/prompt/preset
* Execute provider API call
* Save output to disk

---

## Generation Log

**Commands Executed:**

```powershell
python -m uv run ai-content music --prompt "Smooth instrumental jazz with saxophone and piano, relaxed tempo" --style jazz --provider lyria --duration 30
python -m uv run python examples/lyria_example_ethiopian.py --style ethio-jazz --duration 30
python -m uv run python examples/lyria_example_ethiopian.py --style tizita-blues
python -m uv run python examples/lyria_example_ethiopian.py --style eskista-dance
python -m uv run ai-content music --prompt "Instrumental ethio-jazz fusion with krar-inspired melodies" --provider aimlapi --duration 30
```

**Prompts Used & Reasoning:**

* Jazz: Smooth, relaxed, instrumental to test Lyria capabilities
* Ethio-jazz/Tizita/Eskista: Explore cultural presets and AIMLAPI output
* Custom prompt: Fusion of traditional instruments to test AIMLAPI prompt handling

**Results Achieved:**

* 4 audio tracks generated successfully (30s each)
* Video generation failed due to SDK mismatch
* Screenshots and file sizes documented in project folder

---

## Challenges & Solutions

| Challenge                          | Solution                               |
| ---------------------------------- | -------------------------------------- |
| Windows `uv` not recognized        | Use `python -m uv`                     |
| Veo video generation failed        | Documented and focused on audio        |
| KlingAI authentication unavailable | Skipped provider                       |
| API key configuration              | Verified `.env` for Gemini and AIMLAPI |

---

## Insights & Learnings

* Multi-provider modularity is strong; pipelines abstract complexity
* Presets greatly simplify repeated content generation
* Video generation currently fragile with SDK mismatches
* Windows users need CLI adjustments
* Compared to other AI tools, modular and preset-based workflow is highly flexible

---

## Links

**Google Drive Audio Links:**

* Jazz Audio Track (Gemini / Lyria): [Drive Link](https://drive.google.com/file/d/1CKAH1g6ylVd2cZV4qPMz-W6Q7Oy9oo_g/view?usp=sharing)
* Ethio-jazz Track (AIMLAPI): [Drive Link](https://drive.google.com/file/d/17axHkRv8mekBe7bDgvdUsPXqCGjXlyNl/view?usp=sharing)
* Tizita Blues Track (AIMLAPI): [Drive Link](https://drive.google.com/file/d/12kHdQuwoUQgoKtd_5ojlOIyozsP_Y5AH/view?usp=sharing)
* Eskista Dance Track (AIMLAPI): [Drive Link](https://drive.google.com/file/d/1wV1mffyJwNMSVi4BICHcg97y0WBlOQOw/view?usp=sharing)

**Video Generation Note:**
•	Video generation did not work due to SDK mismatch with Google Gemini / Veo.
•	All submission content consists of audio tracks only.

```
Prompt: "Smooth instrumental jazz with saxophone and piano, relaxed tempo"
Provider: Google Gemini / Lyria
Preset: Jazz
Creative Decisions: Focused on smooth jazz mood, instrumental only, 30-sec duration
```

[Project & outputs](https://github.com/mihretupg/trp1-ai-artist)

