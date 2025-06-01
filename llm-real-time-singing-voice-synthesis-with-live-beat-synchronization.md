

# **LLM-Controlled Real-Time Singing Voice Synthesis with Live Beat Synchronization**


## **1. Introduction**


### **1.1. Problem Statement: The Challenge of Achieving Expressive, Real-Time, Beat-Synchronized Singing using LLMs**

The central research problem addressed herein is the development and rigorous evaluation of a system enabling Large Language Models (LLMs) to control Singing Voice Synthesis (SVS) in real-time, achieving precise synchronization with a live audio beat. This endeavor stands at the confluence of rapidly advancing fields—LLMs, SVS, and real-time audio processing—yet presents a formidable set of challenges. The core difficulty lies in seamlessly integrating the expressive and interpretive capabilities of LLMs with the stringent demands of high-quality vocal synthesis and the temporal accuracy required for musically coherent beat synchronization, particularly when the rhythmic source is live and potentially dynamic.<sup>1</sup>

Current SVS systems, while increasingly sophisticated in vocal quality and stylistic control, are not inherently designed for the kind of dynamic, beat-level temporal adjustments that an LLM might dictate in response to live rhythmic input. Similarly, LLMs, despite their remarkable generative capabilities, often introduce computational latency that is antithetical to the requirements of real-time musical interaction.<sup>1</sup> Therefore, this research confronts a multifaceted problem: generating sung vocals that are not only of high acoustic quality and expressively rich, guided by an LLM's understanding of lyrics and musical context, but also meticulously timed to an external rhythmic source, all within the tight constraints of a live performance scenario. This necessitates addressing significant hurdles in minimizing system latency, ensuring accurate and musically natural lyric-to-beat alignment, managing the substantial computational resources demanded by both LLMs and SVS models, and overcoming the prevalent scarcity of specialized training data suitable for this nuanced task.<sup>1</sup>


### **1.2. Motivation and Significance: Advancing Human-AI Musical Co-Creation and Interactive Performance**

The successful realization of an LLM-controlled, beat-synchronized SVS system would represent a significant leap forward in human-computer interaction (HCI) and the burgeoning field of AI-driven music creation and performance.<sup>1</sup> Such a system promises to unlock a plethora of novel applications. These include, but are not limited to, interactive AI vocalists capable of performing alongside human musicians in real-time, dynamic AI-powered backing singers that can adapt to the nuances of a live band, adaptive music generation systems for immersive experiences in gaming and virtual reality, and innovative expressive tools that could empower artists, composers, and performers in unprecedented ways.<sup>1</sup>

The primary motivation for this research extends beyond mere technological novelty; it is driven by the vision of transforming AI from a static tool for offline music generation into an active, responsive, and co-creative musical partner.<sup>1</sup> The ability for an AI to synchronize its vocal output with a live, dynamic beat is a fundamental prerequisite for systems that can participate meaningfully in the fluid, often improvisational, nature of live musical performance. This aligns with the forward-looking concept of "AI vocalist agents" <sup>1</sup>—intelligent entities that can not only synthesize vocals but also perceive, interpret, and react within a musical ensemble. By tackling the challenges of real-time beat synchronization, this research aims to lay a crucial foundation for a future where humans and AI can collaborate more deeply and intuitively in the creation and experience of music.


### **1.3. Core Research Questions**

To guide this investigation, the following core research questions (RQs) are posed:



* **RQ1:** How can LLM architectures be optimized or adapted to effectively interpret dynamic, real-time beat information—encompassing not only Beats Per Minute (BPM) and beat event timestamps but also metrical structure (downbeats, time signatures) and potentially expressive rhythmic nuances (e.g., groove, swing)—and translate this interpretation into precise, musically coherent control signals for an SVS engine with minimal latency? (Derived from <sup>1</sup>).
* **RQ2:** What systemic architectural patterns—such as reactive LLM control, LLM as a real-time score or parameter generator, or hybrid models as outlined in the foundational document <sup>1</sup>, and potentially informed by broader LLM agent patterns <sup>2</sup>—offer the most advantageous trade-off between minimizing end-to-end system latency, maximizing the expressivity of the synthesized vocals, and ensuring robust accuracy in beat synchronization?
* **RQ3:** How can a "rhythmic common ground"—a novel intermediate representation (IR) specifically designed for musical timing and rhythmic expression—be developed and implemented such that it is sufficiently expressive to capture musical nuance, efficiently generatable by an LLM in a real-time context, and precisely translatable into SVS control parameters for accurate acoustic rendering? (Inspired by <sup>1</sup> and the general need for effective IRs in LLM-driven systems <sup>6</sup>).
* **RQ4:** What are the psychoacoustic perceptual thresholds for beat desynchronization in LLM-generated singing—specifically, the Just Noticeable Differences (JNDs) for rhythmic asynchrony between the synthesized voice and a live beat—and how can these human-centric thresholds be leveraged to guide the design of system latency targets, synchronization accuracy goals, and evaluation protocols? (Implicit from <sup>1</sup>, and informed by existing research on musical latency and synchronization perception <sup>10</sup>).
* **RQ5:** Moving beyond strict metronomic precision, how can the LLM be empowered to interpret the musical style and characteristics of the live beat to generate nuanced expressive timing variations (e.g., micro-timing deviations, dynamic accents, agogic effects like rubato, or stylistic interpretations like swing feel) in the synthesized vocals, thereby fostering a more musically intelligent and less robotic performance? (Derived from <sup>1</sup>, and supported by research in expressive performance modeling <sup>9</sup>).


### **1.4. Research Objectives (SMART)**

The following Specific, Measurable, Achievable, Relevant, and Time-bound (SMART) objectives will guide the execution of this research:



* **O1 (System Architecture & Latency Reduction):** To design, implement, and comparatively evaluate at least two distinct architectural frameworks for LLM-controlled, beat-synchronized SVS (e.g., a hybrid model employing LLM for macro-control and a faster module for micro-timing, versus a fully reactive LLM-driven model). The quantifiable target is to achieve an average end-to-end latency (from live beat detection to audible vocal output) below 100 milliseconds for at least 90% of generated short vocal segments (e.g., 1-2 seconds), a threshold informed by perceptual studies on interactive music systems.<sup>11</sup>
* **O2 (LLM Rhythmic Interpretation & Control):** To develop and empirically validate an LLM-based module capable of processing real-time beat data (including BPM, beat timestamps, and identified downbeats) alongside lyrical input. This module will generate control signals (either via the "rhythmic common ground" defined in O3 or as direct SVS parameters) that result in synthesized vocals demonstrating a mean beat alignment error of less than ±20 milliseconds relative to the target beat events for musically simple, stable rhythms.
* **O3 (Rhythmic Common Ground Development):** To propose, prototype, and evaluate the efficacy of at least one novel intermediate rhythmic representation. This representation must be designed to facilitate precise and expressive timing communication between the LLM and SVS modules, demonstrating its capacity to encode not only fundamental note onsets and durations but also at least two distinct expressive timing articulations (e.g., staccato rendering of a syllable on a beat, legato phrasing across multiple beats).
* **O4 (Expressive Rhythmic Performance):** To investigate and implement at least one strategy enabling the LLM to generate musically appropriate expressive timing variations in the synthesized vocals. These variations (e.g., controlled micro-timing deviations from a strict metronomic grid, or dynamic accents based on inferred beat strength) should be perceptibly different from strictly metronomic output and rated as musically plausible in subjective evaluations by at least three expert listeners.
* **O5 (Comprehensive Evaluation Framework):** To establish and apply a multi-faceted evaluation framework. This framework will incorporate a minimum of three objective technical metrics (e.g., end-to-end latency, synchronization error quantified using F-measure, SVS audio quality measured by Mel Cepstral Distortion) and three subjective assessment dimensions (e.g., perceived musicality of the performance, naturalness of beat synchronization, and perceived interactivity, each rated on a 7-point Likert scale by a panel of at least 10 listeners). The developed system will be rigorously benchmarked against defined baselines.


### **1.5. Scope and Delimitations of the Research**



* **In Scope:** The primary focus of this research is on **monophonic singing voice synthesis**. It will involve a thorough investigation of various LLM architectures, specifically evaluating their suitability for rhythmic understanding and the generation of precise, real-time control signals. A core component will be the implementation and integration of **real-time beat tracking** from a live audio input, which is assumed to be predominantly percussive or possess a clear rhythmic pulse. The project will emphasize the **adaptation, integration, and novel control of existing open-source SVS technologies** rather than the development of entirely new SVS engines from the ground up. A significant research thrust will be the development of innovative **synchronization logic** and the proposed **"rhythmic common ground" representation**. The evaluation strategy will comprehensively cover system performance with respect to latency, synchronization accuracy, and the perceived musical quality and expressiveness of the output.
* **Out of Scope (for initial phases):** The generation of **polyphonic or harmonic singing** (e.g., multiple vocal lines, harmonies) is considered beyond the initial scope, though findings might inform future extensions. Similarly, complex **real-time harmonic analysis by the LLM** for tasks such as automated vocal harmonization will not be a primary focus. The system will not be tasked with generating **accompanying instrumental music**; it will focus solely on the sung vocal line. Handling highly **ambiguous, non-metrical, or extremely complex polyrhythmic inputs** from the live beat source is also outside the initial scope; the research will assume a reasonably discernible beat. Furthermore, the LLM will not be responsible for **de-novo lyrical generation**; lyrics will be provided as input to the system.

The fundamental innovation sought in this research lies at the intersection of LLM-driven generative AI and real-time audio signal processing. While both fields are advancing rapidly, their integration for tasks demanding low latency and high temporal precision, such as live musical performance, remains a significant challenge. LLMs typically operate with higher computational overhead and latency, often in offline generation scenarios.<sup>1</sup> Conversely, real-time audio systems, like the Tungnaá voice synthesizer aiming for sub-100ms latency <sup>26</sup>, prioritize speed. This research aims to bridge this divide by developing methods to make LLMs "performant" within this demanding interactive loop. This might involve careful architectural choices <sup>1</sup>, model optimization techniques (such as Test-Time Compute <sup>27</sup>), or by strategically defining the LLM's role to manage its computational load (e.g., focusing on macro-level expressive control).

Moreover, the concept of "live beat synchronization" as envisioned here extends beyond mere technical alignment. It points towards endowing the LLM with a degree of musical intelligence, enabling it to interpret rhythmic nuances—such as groove, feel, and patterns of emphasis—from the live beat and reflect these subtleties in the SVS output.<sup>1</sup> This elevates the LLM's function from that of a simple controller to a more responsive and "musical" partner, capable of a quasi-improvisational interaction. This pursuit of musical intelligence is a key differentiator from systems that might only achieve metronomic accuracy.

A critical dependency chain exists: excessive system latency (Objective O1) will inevitably compromise the accuracy of beat synchronization (Objective O2). If the system cannot react quickly enough, the synthesized vocals will lag behind the live beat, making precise alignment impossible.<sup>1</sup> This, in turn, would render any attempts at generating nuanced expressive timing (Objective O4) musically jarring and ineffective, as even the most sophisticated expressive intent from the LLM would be delivered out of time. Therefore, successfully addressing latency is a foundational prerequisite for achieving the other research objectives, particularly those related to synchronization and expressive performance.

The broader implications of this research are substantial, potentially contributing to a paradigm shift where AI systems evolve from tools for offline content creation to active, real-time participants in live artistic performances. This could redefine collaborative music-making, open new avenues for music education where students interact with responsive AI tutors, and inspire the design of novel interactive artistic experiences and digital musical instruments.<sup>1</sup>


## **2. Background and State-of-the-Art**


### **2.1. Review of LLMs in Music Generation and Control**

Large Language Models (LLMs) have demonstrated remarkable capabilities in processing and generating sequential data, leading to their increasing application in the music domain. Their use spans symbolic music generation, direct audio synthesis, and the control of musical parameters.<sup>22</sup> Surveys such as "Foundation Models for Music" <sup>22</sup> and "A Survey on Cross-Modal Interaction Between Music and Multimodal Data" <sup>35</sup> provide comprehensive overviews of how foundation models, including LLMs and diffusion models, are architected, pre-trained, and utilized for music understanding and generation, often involving multimodal inputs.

In symbolic music generation, LLMs like ChatMusician have shown proficiency in working with text-compatible representations such as ABC notation, which inherently encodes rhythmic information and musical structure.<sup>45</sup> Similarly, text2midi demonstrates LLMs generating MIDI files from textual descriptions, with controllability over music theory terms including tempo.<sup>47</sup> NotaGen further applies LLM training paradigms (pre-training, fine-tuning, reinforcement learning) to classical sheet music generation, emphasizing musicality and structural coherence.<sup>36</sup> These examples are pertinent as they illustrate LLMs' capacity to handle symbolic formats that explicitly contain timing and rhythmic data, a crucial aspect for beat-synchronized SVS.

LLMs are also being explored for their ability to model and generate expressive musical performances. For instance, the CrossMuSim framework utilizes LLMs to generate rich textual descriptions for music similarity modeling, implying an understanding of complex musical concepts.<sup>34</sup> The CFE+P model, a transformer-based system, predicts notewise dynamics and micro-timing adjustments from inexpressive MIDI input, showcasing the potential for AI to imbue music with human-like expressiveness.<sup>24</sup> Another approach involves a hybrid LLM-LSTM model where MIDI is encoded as text for LLM processing, aiming to combine the structural understanding of LLMs with the temporal consistency of LSTMs.<sup>48</sup> These studies suggest that LLMs can learn and reproduce nuanced performance details beyond basic note information.

Despite these advancements, significant challenges remain in applying LLMs to real-time music generation and control. Chief among these are the inference speed of large models and the difficulty in achieving fine-grained, temporally precise control necessary for tasks like beat synchronization.<sup>8</sup> Some recent open-source frameworks are beginning to address these real-time aspects. Step-Audio, for example, is an open-source framework for intelligent speech interaction that aims for real-time performance by tokenizing audio streams and employing an LLM in its pipeline.<sup>4</sup> Systems like Text2midi-InferAlign <sup>49</sup> and ACE-Step <sup>50</sup> explore inference-time optimization techniques and methods to improve control granularity in LLM-based music generation.

Architecturally, LLM-centric designs are emerging for voice and speech interaction. VocalNet <sup>1</sup> and the aforementioned Step-Audio <sup>4</sup> are examples. MiniMax-Speech, an autoregressive Transformer-based TTS model, features a learnable speaker encoder and achieves state-of-the-art voice cloning results, demonstrating the power of transformer architectures in speech synthesis.<sup>51</sup> YuE is another notable LLM-based framework specifically for lyrics-to-song generation, capable of producing long-form musical pieces.<sup>37</sup> These systems illustrate current architectural trends and the ongoing effort to enhance the capabilities of LLMs in audio and speech domains, providing a foundation upon which the proposed research can build.


### **2.2. Analysis of Existing Singing Voice Synthesis Technologies for Real-Time Adaptation**

A systematic review of existing SVS projects is paramount to identify suitable candidates for adaptation within a real-time, LLM-controlled, beat-synchronized system. This review considers core SVS technology, LLM control mechanisms (actual or potential), documented real-time features (latency, streaming, inference speed), input modalities for singing and rhythmic control, key strengths and challenges for beat synchronization, and licensing terms. The foundational document <sup>1</sup> provides an initial survey, which is augmented here with more recent research.

**Key SVS Systems and Approaches:**



* **Direct LLM Control:** Projects like Prompt-Singer <sup>1</sup> and TechSinger <sup>1</sup> exemplify this approach. Prompt-Singer allows attribute control (gender, range, volume) via natural language prompts, utilizing a decoder-only transformer and a GPT-3.5 Turbo for training data prompt generation. TechSinger employs prompt-based technique prediction and detailed phoneme-level parameter input. While conceptually aligned with direct LLM influence, these systems would require significant adaptation to process beat-derived control signals in real-time and ensure low-latency SVS inference. Their current CLI-based nature <sup>1</sup> presents an engineering challenge for server deployment.
* **LLM for Intermediate Representation:** GPT-SoVITS <sup>1</sup> uses a Generative Pre-trained Transformer (GPT) to produce audio semantic tokens from text, which a SoVITS model then synthesizes. Its strength lies in few-shot voice cloning for singing. The challenge for beat synchronization is to condition this semantic token generation on live beat data in a way that influences timing with low latency. Community-developed API wrappers, some offering streaming, exist.<sup>1</sup>
* **Traditional SVS with LLM-Generated Input:** Mature SVS engines like NNSVS <sup>1</sup> (neural network-based, processes MusicXML/UST) and DiffSinger <sup>1</sup> (diffusion-based, score-conditioned) offer high-quality output from score-like inputs. An LLM could act as a real-time composer, generating these scores. However, the speed of LLM score generation and the SVS inference for short segments are critical bottlenecks.<sup>1</sup>
* **UTAU-like Workflow:** OpenUTAU combined with UIAL (UTAU-Interfacing API Library) <sup>1</sup> allows programmatic generation of UTAU project files. An LLM could drive UIAL to create these files in near real-time for synthesis by backends like NNSVS or DiffSinger. This offers granular control but introduces potential latency in the multi-step pipeline.
* **Relevant TTS Systems with Rhythmic Control Potential:** Some general-purpose TTS systems possess features that might be adapted. Spark-TTS mentions pitch and rate control.<sup>1</sup> XTTS-v2 is known for voice cloning and streaming capabilities (time to first chunk ~200ms).<sup>1</sup> OpenVoice v2 offers flexible voice style control, including an intriguing "rhythm" parameter.<sup>1</sup> The key is whether these controls are sufficiently fine-grained and responsive for precise beat-synchronized singing.
* **Recent Advanced SVS/Audio Generation Systems:**
    * **TCSinger 2** <sup>77</sup> is a multi-task, multilingual, zero-shot SVS model enabling style control via textual (using FLAN-T5-large), speech, or singing prompts. It employs a flow-based custom transformer. While flow-matching can accelerate inference, the paper notes that generation speed still requires improvement for industrial real-time demands.
    * **LLFM-Voice** <sup>72</sup> presents a unified framework for emotionally expressive speech and SVS using LLMs and Flow Matching. It features a fine-grained emotional generator for singing, integrating vocal techniques, tension, and pitch. Flow matching is highlighted for higher generation efficiency, but specific real-time performance for interactive singing is not detailed.
    * **CSSinger** <sup>79</sup> is an end-to-end SVS method employing chunkwise streaming inference with VAE latent representations specifically to address latency. It reportedly achieves significantly lower latency than parallel baseline systems, making it a strong candidate for real-time applications.
    * **Tungnaá** <sup>26</sup> is a real-time voice synthesis instrument built with a Tacotron2-style alignment model and a RAVE vocoder, explicitly targeting latency below 100ms on a CPU. Its emphasis on real-time interaction and customization is highly relevant.
    * **VersBand** <sup>80</sup> is a multi-task song generation framework. Its VocalBand component uses a flow-matching method for generating singing styles, pitches, and mel-spectrograms, aiming for fast, high-quality vocal generation with style control.
    * **Step-Audio** <sup>4</sup> is an open-source framework for intelligent speech interaction, featuring an optimized real-time inference pipeline with a streaming audio tokenizer and an LLM foundation. While speech-focused, its architectural principles for real-time LLM-audio interaction are valuable.

**Evaluation Criteria for Suitability in Beat-Synchronized SVS:**



1. **Control Mechanisms:** The granularity and type of control available over vocal parameters (pitch, duration, phoneme timing, timbre, expressive effects) are crucial. The ideal system would allow an LLM to modulate these parameters precisely and dynamically in response to beat information. For example, TechSinger's per-phoneme parameter input <sup>1</sup> offers fine control, while LLFM-Voice's generator for vocal techniques, tension, and pitch <sup>72</sup> suggests pathways for expressive control.
2. **Real-Time Performance:** This encompasses several factors:
    * **Latency:** Low end-to-end latency is paramount. Systems like XTTS-v2 (reporting ~200ms to first audio chunk <sup>1</sup>), CSSinger (designed for low latency streaming <sup>79</sup>), and Tungnaá (targeting &lt;100ms <sup>26</sup>) are of particular interest.
    * **Streaming:** The ability to process input and output audio in small chunks significantly reduces perceived latency. GPT-SoVITS (via community APIs <sup>1</sup>) and XTTS-v2 <sup>1</sup> support streaming.
    * **Inference Speed & Optimization:** The inherent speed of the SVS model and its amenability to optimization techniques (e.g., quantization, pruning, specialized hardware). Flow-matching, used in LLFM-Voice <sup>72</sup> and VersBand <sup>80</sup>, is noted for efficiency. VocalNet's Multi-Token Prediction (MTP) <sup>1</sup> is another acceleration technique.
3. **Hostability and APIs:** Practical deployment requires well-documented APIs, server components, and ideally, Docker support for ease of setup and integration.<sup>1</sup> The GSVI plugin for GPT-SoVITS <sup>61</sup> provides a user-friendly API. Projects like Dia and OpenVoice v2 also have server implementations.<sup>1</sup> Command-Line Interfaces (CLIs) are useful for non-GUI operation and automation.
4. **Licensing:** The licensing terms (e.g., MIT, Apache 2.0, AGPL, CPML) directly impact the research's ability to modify, build upon, and disseminate the work, as well as potential future applications.<sup>1</sup> Permissive licenses generally offer more flexibility.

**Table 2.2.1: Comparative Analysis of SVS Projects for Real-Time Beat-Synchronized Singing**

This table synthesizes information from <sup>1</sup> and supplementary sources to provide a focused comparison of SVS technologies relevant to the research objectives. It serves as a critical tool for selecting candidate SVS modules for adaptation and integration. The ability to directly compare diverse SVS approaches against the specific requirements of low latency, fine-grained LLM-driven rhythmic control, and beat-synchronization potential is invaluable for making informed design choices and identifying areas where innovation is most needed. For instance, if the table reveals that no existing system perfectly combines low-latency streaming with the desired level of LLM-driven expressive rhythmic control, it strongly justifies the research proposed to bridge this gap. Furthermore, assessing hostability and licensing aids in practical feasibility assessments.


<table>
  <tr>
   <td><strong>Project Name</strong>
   </td>
   <td><strong>Core SVS Technology</strong>
   </td>
   <td><strong>LLM Control Mechanism (Actual/Potential)</strong>
   </td>
   <td><strong>Documented Real-Time Features (Latency, Streaming, Fast Inference, MTP, CLI/API, Hardware Req.)</strong>
   </td>
   <td><strong>Input for Singing (and rhythmic control potential)</strong>
   </td>
   <td><strong>Key Strengths for Beat Synchronization</strong>
   </td>
   <td><strong>Key Challenges for Beat Synchronization</strong>
   </td>
   <td><strong>Licensing</strong>
   </td>
  </tr>
  <tr>
   <td>Prompt-Singer <sup>1</sup>
   </td>
   <td>Transformer-based SVS, GAN vocoder <sup>58</sup>
   </td>
   <td>Direct LLM prompt for attributes (gender, range, volume).<sup>1</sup> LLM (GPT-3.5 Turbo) used for training data prompt generation.<sup>56</sup>
   </td>
   <td>CLI inference.<sup>1</sup> High computational overhead, considerable inference latency from transformer backbone.<sup>58</sup> NVIDIA V100 GPU used.<sup>58</sup>
   </td>
   <td>Text prompts, lyrics, phoneme duration, decoupled pitch (avg F0 for range, rescaled F0 for melody).<sup>56</sup>
   </td>
   <td>Direct high-level control via prompts could adapt to beat-related instructions. Duration input offers timing handle.
   </td>
   <td>LLM latency for prompt generation; translating beat data to effective prompts; SVS inference speed; adapting for dynamic rhythmic cues.
   </td>
   <td>Not specified, but authors note misuse may lead to copyright issues and plan constraints.<sup>58</sup> (GitHub repo has MIT <sup>83</sup>)
   </td>
  </tr>
  <tr>
   <td>TechSinger <sup>1</sup>
   </td>
   <td>Flow-matching based generative model <sup>1</sup>
   </td>
   <td>LLM technique prediction from prompts; detailed phoneme-level parameter input (note pitch, duration, technique per phoneme) <sup>1</sup>
   </td>
   <td>CLI inference.<sup>1</sup> Real-time performance not detailed.
   </td>
   <td>Phonemes, note pitch/duration, technique per phoneme.<sup>1</sup>
   </td>
   <td>Fine-grained per-phoneme control of duration and technique.
   </td>
   <td>LLM generating detailed, timed phoneme sequences rapidly; SVS inference speed.
   </td>
   <td>Not specified in snippets.<sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>GPT-SoVITS <sup>1</sup>
   </td>
   <td>GPT + SoVITS (VITS-based) <sup>1</sup>
   </td>
   <td>LLM (GPT) generates semantic tokens from text for SoVITS.<sup>1</sup>
   </td>
   <td>Community APIs (e.g., GSVI <sup>61</sup>) offer streaming, Gradio WebUI.<sup>59</sup> Core model speed depends on GPT and SoVITS components. Docker support available.<sup>62</sup>
   </td>
   <td>Text, reference audio for voice cloning (0-shot/few-shot).<sup>1</sup>
   </td>
   <td>Excellent voice cloning for singing; potential to condition GPT on beat data for timed token generation.
   </td>
   <td>Indirect control over timing via token generation; combined latency of GPT and SoVITS; reference audio emotion is static.<sup>59</sup>
   </td>
   <td>MIT License.<sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>NNSVS <sup>1</sup>
   </td>
   <td>Neural Network-based (HMM/DNN-style recipes), vocoder-based <sup>66</sup>
   </td>
   <td>LLM generates input score (MusicXML, UST).<sup>1</sup>
   </td>
   <td>Library-based, relies on recipe execution speed. Can be fast for pre-defined scores. Not inherently real-time for dynamic input.
   </td>
   <td>MusicXML, UST files (notes, lyrics, timing).<sup>1</sup>
   </td>
   <td>Score-based precision; mature SVS engine.
   </td>
   <td>LLM generating complete, accurate scores rapidly for short segments; parsing and processing score files in real-time.
   </td>
   <td>MIT License.<sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>DiffSinger <sup>1</sup>
   </td>
   <td>Diffusion probabilistic models, shallow diffusion mechanism <sup>1</sup>
   </td>
   <td>LLM generates input score/parameters.<sup>1</sup>
   </td>
   <td>CLI inference; some community server projects. PNDM plugin to accelerate.<sup>74</sup> Speed depends on diffusion steps and model size. Interactive SVS on HuggingFace.<sup>74</sup>
   </td>
   <td>Music score, MIDI-less mode parameters.<sup>1</sup>
   </td>
   <td>High-quality synthesis; score-based precision.
   </td>
   <td>LLM generating scores/parameters rapidly; diffusion model inference speed can be slow.
   </td>
   <td>Core: MIT License.<sup>74</sup> (Some components/datasets like PopCS may have other licenses e.g. CC BY-NC-SA 4.0 <sup>76</sup>).
   </td>
  </tr>
  <tr>
   <td>OpenUTAU + UIAL <sup>1</sup>
   </td>
   <td>Frontend for various backends (NNSVS, DiffSinger, etc.) <sup>1</sup>
   </td>
   <td>LLM programmatically generates UTAU project files via UIAL.<sup>1</sup>
   </td>
   <td>Dependent on backend SVS speed and UIAL script execution.
   </td>
   <td>UTAU project files (.ust,.ustx).<sup>1</sup>
   </td>
   <td>Highly granular UTAU-style control; leverages existing UTAU ecosystem.
   </td>
   <td>Latency of LLM → UIAL → UTAU file → SVS pipeline; complexity of generating detailed UTAU parameters.
   </td>
   <td>OpenUTAU: Various (often GPL); UIAL: MIT License.<sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>VocalNet <sup>1</sup>
   </td>
   <td>LLM (LLaMA-3 based) + Speech Encoder/Decoder/Vocoder <sup>1</sup>
   </td>
   <td>LLM-centric design for voice interaction.<sup>1</sup>
   </td>
   <td>Designed for real-time voice interaction; Multi-Token Prediction (MTP) for speed.<sup>1</sup>
   </td>
   <td>Text (primarily for speech interaction).<sup>1</sup>
   </td>
   <td>Low-latency design focus; MTP.
   </td>
   <td>Primarily speech-focused; SVS extension needed; LLM directly generating beat-synced singing.
   </td>
   <td>Model weights, code publicly available (likely permissive).<sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>XTTS-v2 <sup>1</sup>
   </td>
   <td>Transformer-based TTS
   </td>
   <td>Not inherently LLM-controlled for singing rhythm beyond reference audio style.
   </td>
   <td>Streaming with ~200ms time to first chunk <sup>1</sup>; &lt;150ms streaming latency with PyTorch on consumer GPU.<sup>84</sup>
   </td>
   <td>Text, reference audio (can be sung) for voice and style cloning.<sup>1</sup>
   </td>
   <td>Good voice cloning, streaming capability.
   </td>
   <td>Lacks direct external beat control mechanisms; style is from reference.
   </td>
   <td>Coqui CPML (non-commercial for models).<sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>OpenVoice v2 <sup>1</sup>
   </td>
   <td>Transformer-based TTS
   </td>
   <td>Not inherently LLM-controlled for singing rhythm.
   </td>
   <td>Server implementation available.<sup>1</sup> Real-time performance not detailed.
   </td>
   <td>Text, reference audio for tone color cloning. Control over emotion, accent, rhythm, pauses, intonation.<sup>1</sup>
   </td>
   <td>"Rhythm" control parameter is intriguing if externally drivable by beat data.
   </td>
   <td>Primarily speech-focused; "rhythm" control may not be suitable for melodic singing sync.
   </td>
   <td>MIT License.<sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>TCSinger 2 <sup>77</sup>
   </td>
   <td>Multi-task multilingual zero-shot SVS; BBC Encoder, Custom Audio Encoder, Flow-based Custom Transformer (Cus-MOE) <sup>78</sup>
   </td>
   <td>Textual prompts (via FLAN-T5-large), speech, or singing prompts for multi-level style control.<sup>78</sup>
   </td>
   <td>Flow-matching offers inference acceleration, but speed "still does not meet higher industrial demands." Future work on streaming.<sup>78</sup>
   </td>
   <td>Music scores (lyrics, notations); singing, speech, or textual prompts.<sup>78</sup>
   </td>
   <td>Multi-level style control via various prompts; flow-matching for potential speed.
   </td>
   <td>Generation speed for strict real-time; translating beat data to effective prompts.
   </td>
   <td>Training datasets under CC BY-NC-SA 4.0; model license not specified.<sup>78</sup>
   </td>
  </tr>
  <tr>
   <td>LLFM-Voice <sup>72</sup>
   </td>
   <td>LLM + Flow Matching for SVS/speech; fine-grained emotional generator (vocal techniques, tension, pitch) <sup>72</sup>
   </td>
   <td>LLM for emotion prompting from speech prompts; generator for singing characteristics.<sup>72</sup>
   </td>
   <td>Flow matching offers "higher generation efficiency".<sup>72</sup> Real-time singing potential not explicitly detailed.
   </td>
   <td>Input text, speaker voiceprint, content representation for LLM; lyrics and MIDI for emotional generator.<sup>72</sup>
   </td>
   <td>Fine-grained control over expressive elements; flow matching for efficiency.
   </td>
   <td>Real-time inference speed for interactive singing; LLM latency.
   </td>
   <td>Not specified in snippets.
   </td>
  </tr>
  <tr>
   <td>CSSinger <sup>79</sup>
   </td>
   <td>End-to-end SVS with VAE latent representations
   </td>
   <td>Not directly LLM-controlled in the paper; score-driven.
   </td>
   <td>Chunkwise streaming inference specifically designed for low latency.<sup>79</sup>
   </td>
   <td>Music score (lyrics, pitch, duration).<sup>79</sup>
   </td>
   <td>Achieved lower latency than parallel baselines in streaming SVS.
   </td>
   <td>Integrating LLM control into its streaming VAE framework.
   </td>
   <td>Not specified in snippets.
   </td>
  </tr>
  <tr>
   <td>Tungnaá <sup>26</sup>
   </td>
   <td>Tacotron2-style alignment + RAVE vocoder
   </td>
   <td>Controlled by symbolic text notations (Unicode chars).<sup>26</sup> LLM could generate these notations.
   </td>
   <td>Real-time streaming on CPU, latency &lt;100ms targeted.<sup>26</sup> Interactive GUI, OSC control.<sup>26</sup>
   </td>
   <td>Text (Unicode character sequences) for vocalization.<sup>26</sup>
   </td>
   <td>Very low latency design; interactive manipulation of synthesis.
   </td>
   <td>Mapping LLM output to its unique text notation system effectively for beat sync.
   </td>
   <td>Not specified (Python package).
   </td>
  </tr>
  <tr>
   <td>VersBand <sup>80</sup>
   </td>
   <td>VocalBand: Flow-matching for singing styles, pitches, mel-spectrograms. AccompBand: Flow-based transformer for accompaniment.<sup>80</sup>
   </td>
   <td>Text and audio prompts for control over lyrics, melody, singing/music styles (emotion, techniques, genre, etc.).<sup>80</sup>
   </td>
   <td>Flow-matching for fast vocal generation.<sup>80</sup> Real-time specifics not detailed.
   </td>
   <td>Text prompts (lyrics, styles), audio prompts (voice/music for customization).<sup>80</sup>
   </td>
   <td>High-level style control via prompts; flow-matching for vocal speed.
   </td>
   <td>Latency for full song generation; fine-grained beat-level timing control.
   </td>
   <td>Not specified in snippets.
   </td>
  </tr>
  <tr>
   <td>Step-Audio <sup>4</sup>
   </td>
   <td>LLM (Step-1 130B) + dual-codebook audio tokenizer (semantic & acoustic) + hybrid speech decoder (flow matching & vocoder) <sup>4</sup>
   </td>
   <td>LLM-centric for intelligent speech interaction.<sup>4</sup>
   </td>
   <td>Optimized real-time inference pipeline; streaming-aware architecture with speculative response generation.<sup>4</sup> Tested on 4xA800 GPUs.
   </td>
   <td>Audio streams, text.<sup>4</sup>
   </td>
   <td>Production-ready open-source framework for real-time speech interaction; advanced LLM.
   </td>
   <td>Primarily speech-focused; adapting for singing and precise beat control.
   </td>
   <td>Apache 2.0 for code; model weights under "Source Code and Model License Agreement for Step-1 Model Series".
   </td>
  </tr>
</table>



### **2.3. Current Approaches to Beat Tracking and Synchronization in Music Systems**

The ability to accurately track a live beat and synchronize synthesized audio to it is fundamental to the proposed research. Beat tracking involves identifying the temporal locations of musical beats in an audio signal, often characterized by a Beats Per Minute (BPM) value and the phase of the beat. State-of-the-art real-time beat tracking algorithms typically employ methods such as onset detection (identifying moments of sudden energy increase), spectral flux analysis, comb filtering (to find periodicities), or increasingly, machine learning models trained to predict beat locations.<sup>1</sup> For instance, libraries like Madmom or Librosa provide implementations of various beat tracking algorithms. A specific area of interest is beat tracking in singing voices, as explored in <sup>85</sup>, which uses Self-Supervised Learning (SSL) front-ends like WavLM and DistilHuBERT, followed by a linear transformer, to predict beats directly from vocal signals. This work is relevant if the live audio input for synchronization is itself melodic or contains vocals, and it also details dataset creation strategies and evaluation metrics such as F-measure, P-score, Cemgil, and Goto for beat tracking accuracy.

Once beats are detected, synchronization involves aligning other musical events—in this case, synthesized vocal phonemes or notes—to these beat locations. Digital Audio Workstations (DAWs) and music sequencers commonly use mechanisms like MIDI clock or Ableton Link to synchronize multiple devices or software instances. Interactive Music Systems (IMS) often implement custom logic to align generated events with an incoming rhythm.

Key challenges in live beat tracking include handling tempo drift (gradual changes in tempo), managing complex or ambiguous rhythmic patterns (e.g., syncopation, rubato), and minimizing the latency inherent in the detection process itself. An inaccurate or delayed beat track will inevitably lead to poor synchronization of the SVS output.

Crucially, the perceptual aspects of beat synchronization must inform system design. The Just Noticeable Difference (JND) for rhythmic asynchrony—the smallest timing deviation that a human listener can perceive—sets a critical target for system accuracy and latency. Research in psychoacoustics provides some guidance: JND for amplitude is around 1 dB, while for pitch, it can be around 3 Hz for frequencies below 500 Hz (or ~10 cents above 1000 Hz).<sup>13</sup> For speech melody, JNDs average 1-2 semitones, but differences greater than 3 semitones are more communicatively significant.<sup>13</sup> Studies on Networked Music Performance (NMP) and spatial audio systems offer insights into tolerable latencies for interactive musical tasks, with mean Spatial Audio Latency (SAL) thresholds reported between 128ms and 158ms in some contexts <sup>11</sup>, and other research suggesting that latencies below 100ms are desirable for real-time interaction.<sup>26</sup> Factors like pitch can also bias sensorimotor synchronization to auditory rhythms, affecting perceived timing.<sup>18</sup> Understanding these perceptual limits is vital for defining "real-time" and "synchronized" in a musically meaningful way for this project. Deficits in rhythm perception and entrainment abilities in humans also highlight the complexity of these tasks.<sup>16</sup>


### **2.4. Identification of Key Research Gaps and Opportunities**

Based on the review of LLMs in music, SVS technologies, and beat synchronization, several key research gaps and opportunities emerge, forming the core motivation for this proposed work:



* **Gap 1: LLM Rhythmic Nuance and Real-Time Interpretation:** While LLMs are advancing in symbolic music generation <sup>45</sup> and modeling expressive performance features from static data <sup>24</sup>, their capacity for *real-time interpretation* of live beat information and the *generation of nuanced rhythmic control signals* (e.g., groove, swing, micro-timing adjustments) specifically for SVS remains largely underdeveloped.<sup>1</sup> The challenge is to move LLMs from offline analysis or generation to dynamic, interactive rhythmic agents.
* **Gap 2: SVS Responsiveness to Fine-Grained, Dynamic Rhythmic Control:** Most existing SVS systems are designed to accept either high-level stylistic prompts (which may be too coarse for precise beat synchronization) or detailed, offline score inputs (which are too slow for real-time LLM generation and interaction).<sup>1</sup> There is a significant need for SVS architectures or adaptation methods that allow for dynamic, fine-grained adjustment of vocal parameters (phoneme/note onsets, durations, expressive articulations) in direct response to LLM-generated, beat-informed control signals. While systems like SinTechSVS <sup>86</sup> or LLFM-Voice <sup>72</sup> explore control over singing techniques or emotional expressiveness, direct LLM-driven beat-level expressive timing control is a frontier.
* **Gap 3: Holistic End-to-End Latency Management:** The cumulative latency from live beat detection, through LLM processing for interpretation and control signal generation, to the final SVS audio rendering, poses a formidable barrier to true real-time interaction.<sup>1</sup> While individual components are being optimized (e.g., Test-Time Compute (TTC) for LLMs <sup>27</sup>, streaming SVS like CSSinger <sup>79</sup>), a holistic approach to minimizing latency across the entire integrated pipeline, including inter-component communication and data transformation overhead, is required.
* **Gap 4: A "Rhythmic Common Ground" as an Intermediate Representation:** A major impediment is the lack of a standardized, effective intermediate representation (IR) for rhythm and timing that is simultaneously expressive enough for musical nuance, efficiently generatable and interpretable by an LLM in real-time, and precisely consumable by an SVS engine.<sup>1</sup> General IRs for LLMs are being studied <sup>6</sup>, and rich symbolic music formats like MusicXML or MEI exist <sup>8</sup>, but these are not typically optimized for direct, low-latency LLM generation and SVS consumption in a beat-synchronized loop. A specialized real-time rhythmic IR is needed.
* **Gap 5: Specialized Datasets for Beat-Aware Expressive Singing:** The development and robust evaluation of models capable of beat-synchronized expressive singing are significantly hampered by the scarcity of suitable training and testing datasets.<sup>1</sup> Existing SVS or MIR datasets often lack the detailed, synchronized annotations of beat information, lyrical content, precise phoneme/note timings, and corresponding expressive vocal parameters (e.g., micro-timing deviations, dynamic variations) necessary for this specific task. While general dataset creation and annotation methodologies exist <sup>91</sup>, and some provide rich annotations like Annotated-VocalSet <sup>92</sup> or expressive MIDI features like GigaMIDI <sup>9</sup>, datasets explicitly linking live beat characteristics to expressive vocal performance parameters are rare.

The convergence of LLMs into multimodal audio domains <sup>5</sup> and the increasing controllability of SVS systems <sup>1</sup> creates a fertile ground for this research. However, a critical divergence persists: LLMs often operate in offline or higher-latency scenarios, whereas real-time beat synchronization demands immediate, low-latency responsiveness. This research seeks to bridge this gap, aiming to imbue low-latency SVS with the sophisticated expressive control capabilities of LLMs. This involves tackling the "control granularity vs. LLM instructability" dilemma <sup>1</sup>: highly detailed SVS control offers precision but is challenging for LLMs to manage in real-time, while high-level prompts are LLM-friendly but may lack rhythmic specificity. The proposed "Rhythmic Common Ground" (Objective O3) is conceived as a potential solution, offering a balanced intermediate layer of rhythmic abstraction.

The scarcity of specialized beat-aware expressive singing datasets (Gap 5) has a cascading negative impact. It limits the ability to effectively train LLMs for nuanced rhythmic interpretation (Gap 1) and SVS models for responsive, fine-grained rhythmic control (Gap 2). This data deficit also complicates the development and validation of objective evaluation metrics for these specific capabilities. Therefore, addressing this data gap is not merely a supplementary task but a foundational element for progress in the field.

The open-source ecosystem plays a pivotal role. Many foundational SVS projects (NNSVS, DiffSinger, GPT-SoVITS) are open-source <sup>1</sup>, and community efforts, such as developing API wrappers for GPT-SoVITS <sup>1</sup>, significantly accelerate research and practical application. This research intends to actively leverage these open-source resources and contribute its findings and developed tools back to the community, fostering further innovation.


## **3. Proposed Research Methodology**


### **3.1. Overall Research Design: Iterative and Modular**

The proposed research will adhere to an **iterative and incremental development methodology**. This approach involves breaking down the complex system into manageable components, each undergoing cycles of design, implementation, unit testing, and refinement. This iterative nature allows for flexibility, enabling the research to adapt to unforeseen challenges and incorporate new insights as they emerge. Early and frequent testing of individual modules and their integrations will help identify and mitigate risks proactively.

A **modular system architecture** will be a cornerstone of the design, as strongly advocated in the foundational analysis.<sup>1</sup> This entails developing distinct, well-encapsulated software modules for each primary function: (1) Live Audio Input and Beat Tracking, (2) LLM-based Control/Generation, (3) Core SVS Module & Micro-Timing Adjustment, and (4) Synchronization Logic and Latency Compensation. Each module will have clearly defined Application Programming Interfaces (APIs) to facilitate communication and data exchange. This modularity offers several advantages:



* **Independent Development and Testing:** Teams or individuals can work on different modules concurrently.
* **Component Swappability:** It allows for easier substitution of different algorithms or models within a module (e.g., experimenting with various SVS backends or different LLM architectures) without requiring a complete system overhaul.
* **Maintainability and Extensibility:** The overall system becomes easier to understand, debug, maintain, and extend with new functionalities in the future. The architecture of systems like Step-Audio, an open-source framework for intelligent speech interaction, which emphasizes modularity with components for Voice Activity Detection, Streaming Audio Tokenizer, LLM, and Speech Decoder <sup>4</sup>, can serve as a useful reference for structuring the proposed system.


### **3.2. Architectural Framework for LLM-Controlled Beat-Synchronized SVS**

This research will primarily investigate and develop a **Hybrid Model architecture**, as conceptualized in <sup>1</sup> (Sec 3.4). This architectural choice is motivated by its potential to balance the rich expressive capabilities of LLMs with the stringent low-latency requirements of real-time beat synchronization. In this paradigm, the LLM is responsible for **macro-control**, determining broader stylistic, emotional, and rhythmic intentions based on lyrical input and the overall beat context. A separate, computationally lighter, and faster module, or a highly optimized SVS component, will then handle the **micro-timing adjustments**, ensuring the fine-grained alignment of synthesized vocal events to individual beats. This division of labor aims to prevent the LLM from becoming a bottleneck due to per-beat computational demands, thereby helping to manage overall system latency.

While the Hybrid Model will be the primary focus, alternative architectures, such as a more **Reactive LLM Control** model <sup>1</sup> or an **LLM as Real-Time Score Generator** model <sup>1</sup>, will be developed as comparative baselines or explored for specific sub-studies. The overarching design may also draw inspiration from LLM agent architectures <sup>2</sup>, where the LLM acts as an orchestrator, utilizing specialized "tools" like the beat tracker and the SVS engine to achieve its goal.

The core components of the proposed hybrid architecture are:

**3.2.1. Live Audio Input and Advanced Beat Tracking Module**



* **Input:** This module will capture a live audio stream, expected to be a musical backing track or percussive elements providing a discernible rhythmic pulse.
* **Processing:** It will employ state-of-the-art real-time beat tracking algorithms. Beyond basic BPM and beat timestamps, the aim is to extract richer rhythmic information, such as downbeat positions, inferred time signatures, and potentially characteristics of the musical "feel" (e.g., swing ratio, rhythmic intensity). Techniques from singing beat tracking research <sup>85</sup>, which use SSL front-ends (WavLM, DistilHuBERT), might be adapted if the input audio is melodic or contains vocals, as these methods are designed to handle less percussive rhythmic cues.
* **Output:** The module will produce a continuous stream of beat events (timestamps, beat numbers) and derived rhythmic parameters, which will be fed to the LLM-based Control/Generation Module.
* **Challenge:** A key challenge is ensuring the low-latency, accuracy, and robustness of this beat tracking, especially when faced with dynamic tempi, complex rhythmic patterns, or noisy input signals. Errors or delays in this upstream module will inevitably degrade the performance of the entire system.

**3.2.2. LLM-based Control/Generation Module**



* **Input:** This module, the "brain" of the system, will receive the lyrical content to be sung, the continuous stream of beat information from the beat tracking module, and potentially high-level user prompts regarding desired style or emotion.
* **LLM Architecture & Optimization:** The research will experiment with various LLM architectures, prioritizing those that are efficient and suitable for real-time inference. This may involve using smaller, specialized LLMs fine-tuned for rhythmic and musical tasks, or applying optimization techniques such as quantization or pruning to larger foundation models. The potential of Test-Time Compute (TTC) strategies <sup>27</sup> to enhance LLM responsiveness and reduce inference latency in this audio-centric context will be a specific area of investigation.
* **Rhythmic Interpretation & Macro-Control:** The LLM will be trained or fine-tuned to perform several key functions:
    * Interpret the incoming beat data in a musically meaningful way, moving beyond simple metronomic understanding to grasp aspects of groove or style.<sup>1</sup>
    * Align lyrical phrases and syllables to the underlying beat structure in a musically natural manner, considering prosody and emphasis.
    * Generate high-level rhythmic style parameters or directives (e.g., "sing this phrase staccato on the beat," "apply a crescendo leading into the downbeat," "introduce a slight lay-back feel for this section").
* **Output:** The LLM will output its rhythmic and expressive intentions in the form of the "Rhythmic Common Ground" representation (detailed in Sec 3.3) or as direct high-level control signals destined for the Micro-Timing Adjustment module or the SVS engine. This output might represent, for example, a rhythmically "approximate" melodic contour or a set of prosodic and stylistic targets for a given lyrical segment.

**3.2.3. Core SVS Module & Micro-Timing Adjustment**



* **SVS Engine Selection:** Based on the comparative analysis conducted in Section 2.2 (Table 2.2.1), one or two promising open-source SVS engines will be selected for adaptation. The choice will depend on the nature of the control signals generated by the LLM.
    * If the LLM generates micro-scores or detailed parametric sequences, score-based engines like NNSVS or DiffSinger <sup>1</sup> might be suitable.
    * If the LLM produces attribute modulations or high-level style prompts, direct control systems like an adapted Prompt-Singer or TechSinger <sup>1</sup> could be explored.
    * Systems like GPT-SoVITS <sup>1</sup> might be used if the LLM can effectively influence its semantic token generation in a rhythmically precise manner.
    * Newer models like VersBand's VocalBand, with its flow-matching architecture for style, pitch, and mel-spectrogram generation <sup>80</sup>, or the low-latency CSSinger <sup>79</sup> and Tungnaá <sup>26</sup>, also present viable options.
* **Micro-Timing Adjustment Module:** This crucial component (which could be a standalone module or an enhanced input stage for the SVS engine) will receive the LLM's macro-control output (e.g., via the Rhythmic Common Ground) and the precise beat timings from the beat tracker. Its function is to perform the fine-grained "snapping" or alignment of vocal events (such as phoneme or note onsets and durations) to the exact beat targets. This might involve algorithms for constrained dynamic time warping, real-time adjustment of synthesis parameters based on beat error, or predictive timing adjustments. The "rhythm" control parameter offered by systems like OpenVoice v2 <sup>1</sup> will be investigated to determine if it can be effectively driven by precise external timing data for this purpose. The ability to perform dynamic acoustic parameter adjustment for expressive timing and rhythmic control <sup>54</sup> is central to this module's design.

**3.2.4. Synchronization Logic and Latency Compensation Mechanisms**



* **Core Synchronization:** Robust synchronization logic will be implemented to ensure that the SVS output aligns temporally with the detected beats from the live audio stream.<sup>1</sup> This logic will manage the flow of data and control signals between modules.
* **Latency Compensation Strategies:** Several strategies from <sup>1</sup> (Sec 3.5) will be explored:
    * **Predictive Processing:** If the live beat is relatively stable or predictable (e.g., consistent tempo), the system may anticipate upcoming beats. This lookahead can provide additional processing time for the LLM and SVS components to prepare the corresponding audio segment, thereby reducing perceived latency.
    * **Intelligent Buffering and Jitter Management:** Carefully designed buffering mechanisms can help smooth out variations in the processing times of different components, preventing audible glitches, dropouts, or timing inconsistencies, without sacrificing the overall sense of liveness if buffer sizes are kept minimal.
* **Advanced Synchronization (Future Work):** The potential for closed-loop control mechanisms <sup>1</sup> will be considered as a more advanced research goal. In such a system, the AI would actively monitor its own synthesized audio output relative to the live beat and make continuous, dynamic corrections to maintain or improve synchronization. This is analogous to how human musicians listen and adjust to each other in an ensemble.
* **Model-Specific Optimizations:** If the chosen SVS or LLM components are based on diffusion models or transformers, specific latency reduction techniques developed for these architectures (e.g., for diffusion models <sup>99</sup>; for transformers <sup>51</sup>) will be reviewed and adapted where applicable.

The successful implementation of this hybrid architecture hinges critically on the interface and intermediate representation between the LLM (macro-control) and the micro-timing module. If this interface is overly complex or introduces significant data conversion overhead, it could negate the latency benefits sought by offloading fine-grained timing from the LLM. Therefore, the design of the "Rhythmic Common Ground" (see Sec 3.3) is intrinsically linked to the viability of this architectural approach.


### **3.3. Development of a "Rhythmic Common Ground" Representation**

A pivotal sub-task within this research, addressing Gap 4 (Sec 2.4) and a key challenge identified in <sup>1</sup> (Sec 3.6), is the design and prototyping of a "Rhythmic Common Ground." This refers to an intermediate data representation (IR) specifically tailored for conveying rhythm and timing information effectively between the LLM and the SVS modules in a real-time context. The development of such an IR is crucial because existing formats are often not optimized for this specific tripartite requirement of LLM generatability, SVS consumability, and expressive rhythmic richness within a low-latency loop. While LLMs are being studied for their understanding of general-purpose IRs in programming <sup>6</sup>, and rich symbolic music formats like MusicXML or MEI <sup>8</sup> can encode detailed musical structure, they may be too verbose or complex for efficient real-time generation by an LLM or direct consumption by an SVS system without significant adaptation.

**Objectives for the Rhythmic Common Ground:**



1. **Expressiveness:** The IR must be capable of representing not only basic note onsets and durations but also more nuanced expressive timing elements crucial for musicality. This includes indications for micro-timing deviations (e.g., playing slightly ahead or behind the beat for swing or lay-back feel), accents and dynamic emphasis relative to beat positions, and potentially higher-level rhythmic patterns or stylistic articulations (e.g., staccato, legato, tenuto).
2. **LLM-Generatability:** The IR must be structured in a way that an LLM can efficiently and reliably produce it in real-time. This implies a format that is relatively compact, perhaps text-like (e.g., a specialized markup language or JSON structure), or a simplified symbolic notation that aligns well with the sequential generation capabilities of LLMs. It should avoid overly complex nested structures or binary formats that are difficult for LLMs to generate directly.
3. **SVS-Consumability:** The IR must be directly and unambiguously translatable into the control parameters required by the chosen SVS engine or the micro-timing adjustment module. This translation should be computationally inexpensive to avoid introducing additional latency.

**Proposed Methodology for IR Development:**



1. **Review and Analysis:** A thorough review of existing relevant formats will be conducted. This includes:
    * Standard symbolic music formats: MIDI (especially expressive MIDI concepts like note onset deviations from a grid, as explored in the GigaMIDI dataset analysis <sup>9</sup>), MusicXML, and MEI, focusing on their timing and expression encoding capabilities.
    * Input formats for existing SVS systems: For example, UST files for UTAU-based systems, MusicXML for NNSVS/DiffSinger <sup>1</sup>, or phoneme-level timing inputs for systems like TechSinger.<sup>1</sup>
    * Representations used in computational musicology for expressive performance analysis.
2. **Design Iteration:** Based on the analysis, several candidate IR designs will be conceptualized and prototyped. These designs might explore:
    * **Beat-Relative Timings:** Representing all vocal event timings (e.g., phoneme onsets, note boundaries) relative to the detected beat timestamps, rather than absolute time.
    * **Hierarchical Structure:** Encoding rhythm at multiple levels (e.g., beat, sub-beat, measure) to allow for both broad and fine-grained control.
    * **Explicit Expressive Markers:** Incorporating specific tags or parameters for common expressive articulations (e.g., accent_strength: 0.8, timing_offset: -10ms, articulation: staccato).
    * **Parameterized Rhythmic Motifs:** Defining short, reusable rhythmic patterns that the LLM can invoke and parameterize.
3. **Prototyping and Evaluation:**
    * Implement parsers and generators for the candidate IRs.
    * Test the LLM's ability to generate these IRs based on lyrical and beat inputs in an offline setting.
    * Test the SVS module's ability to synthesize vocals accurately from these IRs.
    * Evaluate the IRs based on compactness, ease of generation/parsing, and expressive range.

The development of this Rhythmic Common Ground is not merely a technical exercise in data formatting; it is fundamental to enabling effective and nuanced communication between the LLM's "musical mind" and the SVS's "voice." A successful IR will act as the linguistic bridge that allows the LLM to precisely convey its rhythmic intentions to the synthesis engine, which is a critical step towards achieving truly expressive, beat-synchronized AI singing.


### **3.4. Strategies for Enhancing Expressive Timing and Musical Interpretation by the LLM**

Achieving musically compelling beat-synchronized singing requires the LLM to go beyond mere metronomic alignment and imbue the performance with expressive timing and interpretation that reflects the character of the live beat and the musical style. This objective addresses Gap 1 (LLM rhythmic nuance) identified in Sec 2.4 and aligns with the vision of a musically intelligent AI performer described in <sup>1</sup> (Sec 3.6, 4.6). The following strategies will be pursued:



1. **LLM Training and Fine-tuning for Musical Expressivity:**
    * **Specialized Datasets:** The LLM will be fine-tuned on datasets specifically curated or created (see Sec 4.4) to include examples of expressive singing performances aligned with detailed beat and rhythmic annotations. This data should ideally capture variations in micro-timing, dynamics, and articulation relative to the musical context. The aim is for the LLM to learn the correlations between input beat characteristics (e.g., a strong downbeat, a syncopated rhythm, a particular groove) and appropriate expressive vocal responses. Research on LLM-based music analysis and generation of expressive features <sup>34</sup> provides a foundation for this.
    * **Transfer Learning:** Pre-trained foundation models with strong sequential understanding (e.g., LLaMA-based models as used in YuE <sup>37</sup> or ChatMusician <sup>46</sup>) will be used as a starting point for fine-tuning, leveraging their existing knowledge of language and potentially music structure.
2. **Advanced Prompt Engineering for Rhythmic Control:**
    * Effective prompting strategies will be designed to allow users (or other AI modules) to guide the LLM's rhythmic interpretation at a high level. This could involve natural language cues (e.g., "sing this phrase with a laid-back bluesy feel," "make the rhythm very tight and punchy," "anticipate the downbeat slightly for emphasis") that the LLM learns to translate into specific modifications of the Rhythmic Common Ground or SVS control parameters.
3. **Modeling Explicit Expressive Parameters:**
    * The LLM will be trained to output not just basic pitch and duration information but also explicit parameters that directly control expressive elements in the SVS engine. This could include:
        * **Micro-timing Deviations:** Values indicating slight shifts (e.g., in milliseconds or as a percentage of beat duration) for phoneme or note onsets relative to the strict metronomic grid. This is inspired by models like CFE+P, which predict micro-timing adjustments for instrumental music.<sup>24</sup>
        * **Dynamic Accents:** Parameters controlling the intensity or loudness of specific syllables or notes, particularly in relation to their position within the beat structure (e.g., emphasizing downbeats or syncopated notes).
        * **Articulation Control:** Tags or parameters indicating desired articulations like staccato, legato, or tenuto, which have significant rhythmic implications.
    * The SVS module will need to be adapted to respond to these fine-grained expressive parameters. Work on fine-grained prosody and technique control in SVS <sup>54</sup> will inform this aspect.
4. **Incorporating Musical Knowledge and Style Awareness:**
    * Methods will be explored to imbue the LLM with a deeper understanding of different musical styles and their associated rhythmic conventions. For example, the LLM could learn to apply specific swing ratios for jazz-style singing or characteristic rhythmic placements for funk or reggae. This might involve training on style-specific datasets or incorporating explicit style embeddings as conditioning input to the LLM.
    * The LLM could also be trained to infer aspects of the musical "feel" from the live beat input itself (e.g., by analyzing patterns of micro-timing or accentuation in the incoming rhythm) and then reflect this feel in the synthesized vocals.

The capacity of the LLM to generate truly *expressive* and *musically nuanced* rhythmic interpretations is fundamentally linked to the quality and nature of the data it is trained on (see Sec 4.4). If the training data primarily consists of metronomically precise performances, the LLM will likely reproduce such an output. To achieve human-like rhythmic expressivity, the LLM must be exposed to, and learn from, examples where expressive timing variations are clearly annotated and correlated with the underlying beat structure and musical context.

The overall success of these strategies will depend on finding the right balance in the hybrid architecture. The LLM should provide the high-level musical intelligence and expressive direction, while the micro-timing module and SVS engine handle the precise, low-latency execution. The Rhythmic Common Ground (Sec 3.3) will be the critical communication channel for these expressive intentions.


## **4. Experimental Design and Implementation Plan**

The research will be conducted in three main phases, following an iterative development approach as outlined in <sup>1</sup> (Sec 5.2). This phased structure allows for systematic development, testing, and mitigation of risks associated with building such a complex, interactive system.


### **4.1. Phase 1: Component Development and Offline Validation**

The primary objective of Phase 1 is to develop and individually validate the core modules of the proposed system in an offline or controlled environment before full integration. This approach allows for focused debugging and optimization of each component.

**4.1.1. Beat Tracking Module Evaluation**



* **Implementation:** At least two to three candidate real-time beat tracking algorithms will be implemented or adapted from existing libraries (e.g., Madmom, Librosa). This will include both traditional signal processing-based methods and more recent machine learning-based approaches, potentially including adaptations of the SSL-based vocal beat tracker described in <sup>85</sup> if applicable to the expected input types.
* **Evaluation Datasets:** The selected algorithms will be evaluated on standard public beat tracking datasets such as GTZAN, Hainsworth, and SMC MIDI to benchmark their performance on diverse musical material. Additionally, a small custom dataset of live audio recordings (e.g., solo drumming, simple backing tracks) with varying rhythmic complexity and manually annotated ground truth beats will be created for more targeted testing.
* **Metrics:** Performance will be assessed using established beat tracking metrics, including F-measure (F1-score), Cemgil score, Goto score, and P-score, as utilized in.<sup>85</sup> Crucially, the processing latency of each beat detection event will be measured to ensure suitability for real-time application.
* **Goal:** Select the beat tracking algorithm (or combination of algorithms) that provides the best balance of accuracy, robustness to rhythmic variations, and low processing latency.

**4.1.2. LLM Rhythmic Interpretation and Control Signal Generation**



* **LLM Module Prototyping:** A prototype LLM module will be developed, likely by fine-tuning a pre-trained foundation model (e.g., a LLaMA-based model, as explored in YuE <sup>37</sup> or ChatMusician <sup>46</sup>, or other efficient architectures). The choice will be guided by factors such as model size, inference speed, and ability to process sequential and structured data.
* **Task Definition:** In this offline setting, the LLM will be tasked with processing pre-recorded beat tracks (sequences of beat timestamps and associated rhythmic features) and corresponding lyrics. Its primary output will be instances of the "Rhythmic Common Ground" representation (developed in Sec 3.3) or, alternatively, direct SVS control parameters if a more reactive architecture is being prototyped as a baseline.
* **Evaluation:** The generated rhythmic representations or control signals will be analyzed offline.
    * **Objective Evaluation:** Structural correctness of the generated IR, adherence to input beat timings, and consistency of rhythmic patterns.
    * **Qualitative Evaluation:** Music experts will assess the musical coherence of the generated rhythmic patterns, their appropriateness for the given lyrics, and their potential to lead to expressive vocal performances.
* **Goal:** Validate the LLM's capability to translate beat and lyric information into a meaningful and usable rhythmic control representation, and to identify initial challenges in LLM-based rhythmic reasoning.

**4.1.3. SVS Responsiveness and Controllability**



* **SVS Adaptation:** The selected SVS engine(s) (from Table 2.2.1) will be adapted to accept the proposed "Rhythmic Common Ground" representation or other fine-grained control signals as input. This may involve modifying the SVS model's input layers or developing a pre-processing module that translates the IR into the SVS's native parameter space.
* **Controlled Testing:** The adapted SVS module will be tested using synthetic control signals that simulate the expected output from the LLM. These synthetic signals will include precise timings for phonemes/notes and variations in expressive parameters.
* **Metrics:**
    * **Audio Quality:** Objective metrics such as Mel Cepstral Distortion (MCD) and subjective Mean Opinion Score (MOS) tests will assess the acoustic quality of the synthesized vocals.
    * **Pitch Accuracy:** F0 Root Mean Square Error (F0-RMSE) and F0 Correlation (F0-CORR) will measure how accurately the synthesized pitch follows the control signals (metrics from VERSA toolkit <sup>103</sup>).
    * **Timing Accuracy:** The temporal precision of synthesized phoneme or note onsets and durations will be measured against the timings specified in the synthetic control signals. This is a critical measure of the SVS's responsiveness to rhythmic instructions.
* **Goal:** Ensure that the SVS engine can faithfully render vocals based on the detailed rhythmic and expressive instructions it receives, and to quantify its inherent latency and processing speed for short vocal segments.


### **4.2. Phase 2: Integrated System Prototyping and Near Real-Time Testing**

Following the successful validation of individual components, Phase 2 will focus on integrating these modules into an initial end-to-end pipeline.



* **Implementation:** The beat tracker, LLM module, and adapted SVS engine will be interconnected. Initial synchronization logic will be developed to manage the data flow and timing between these components.
* **Testing Environment:** The integrated system will initially be tested using pre-recorded audio files as the beat source or stable, machine-generated beat patterns (e.g., from a MIDI sequencer). This controlled environment allows for repeatable experiments and easier debugging of integration issues.
* **Performance Measurement:**
    * **Latency Analysis:** Component-wise and end-to-end latency will be meticulously measured. This involves timestamping data as it passes through each stage of the pipeline (beat detection → LLM processing → SVS rendering → audio output).
    * **Synchronization Accuracy:** The system's ability to synchronize the SVS output with the known, stable beat inputs will be assessed.
* **Optimization:** Bottlenecks in the pipeline will be identified and iteratively optimized. This phase will be critical for exploring and implementing latency mitigation strategies, such as efficient data transfer protocols, model quantization for the LLM and/or SVS, and potentially applying Test-Time Compute (TTC) strategies <sup>27</sup> to improve the LLM's inference speed without extensive retraining.
* **Goal:** Achieve a functional end-to-end system capable of operating in near real-time with stable beat inputs, and to understand the primary sources of latency and synchronization error in the integrated pipeline.


### **4.3. Phase 3: Live Beat Synchronization and Interactive Performance Experiments**

This phase represents the ultimate test of the system's capabilities, evaluating its performance with live, dynamic audio input and in interactive scenarios.



* **Testing Setup:**
    * **Live Input:** The system will be connected to a live audio source, such as a human musician playing a percussion instrument (e.g., drum kit, cajon) or a rhythm instrument (e.g., guitar, keyboard) providing a clear rhythmic backing.
    * **Interactive Performance:** The system will generate sung vocals in real-time based on the live beat input and pre-defined lyrical content.
* **Participants:**
    * **Musicians:** Experienced musicians will be recruited to provide the live beat input. Their ability to play with varying degrees of rhythmic complexity, tempo, and expressive feel will be important for testing the system's adaptability.
    * **Listeners:** Both expert listeners (e.g., musicians, audio engineers) and naive listeners will be recruited for subjective evaluation sessions.
* **Data Collection:**
    * **Objective Data:** Continuous logging of end-to-end latency, beat detection accuracy, and synchronization error between the live beat and the SVS output.
    * **Subjective Data:** Questionnaires and structured interviews will be used to gather feedback from interacting musicians (regarding perceived responsiveness, predictability, controllability, and creative potential of the system) and from listeners (regarding musicality, expressiveness, naturalness of synchronization, and overall engagement). Evaluation frameworks from Human-Computer Interaction (HCI) and New Interfaces for Musical Expression (NIME) research will be adapted.<sup>105</sup>
* **Experimental Conditions:** Tests will be conducted under various conditions, such as different musical genres/styles implied by the beat, varying tempi, and different levels of rhythmic complexity provided by the live musician.
* **Goal:** To rigorously evaluate the system's performance in a realistic live setting, assess its ability to handle dynamic and unpredictable rhythmic input, and gather comprehensive data on its technical efficacy and perceived musical quality.

The phased experimental design is a deliberate strategy to mitigate the high risks associated with building a complex real-time interactive system. By validating components offline first, the research can systematically address technical challenges and refine algorithms before tackling the complexities of live integration. This iterative process also acknowledges that system optimization is often a journey of identifying and resolving evolving bottlenecks: initial performance limitations might reside within individual components (like LLM inference speed), but as these are addressed, new bottlenecks may emerge in inter-component communication, data conversion, or the synchronization logic itself. The experimental plan must therefore remain flexible to adapt to these discoveries.


### **4.4. Dataset Strategy**

The availability of appropriate datasets is crucial for training the LLM component, fine-tuning the SVS module, and rigorously evaluating the overall system. This research will employ a multi-pronged dataset strategy:

**4.4.1. Leveraging Existing Datasets**



* **SVS Model Training/Fine-tuning:** Publicly available SVS datasets such as M4Singer <sup>109</sup>, Opencpop, PopBuTFy, and potentially VCTK (for voice cloning aspects if needed) will be utilized for training or fine-tuning the core SVS engine. The choice will depend on the selected SVS technology and its data requirements. <sup>1</sup> mentions several such datasets.
* **Beat Tracking Module Evaluation:** Standard beat tracking datasets (e.g., GTZAN, Hainsworth, SMC MIDI, and those listed in <sup>85</sup>) will be used to benchmark the performance of the selected beat tracking algorithms.
* **LLM Pre-training/Fine-tuning (General Musicality):** While not the primary focus for rhythmic training, existing large-scale music datasets (e.g., MIDI collections like the Lakh MIDI Dataset or GigaMIDI <sup>9</sup> for symbolic understanding, or audio datasets if the LLM processes audio features) can provide a foundation for general musical knowledge before specialized rhythmic fine-tuning. GigaMIDI, with its heuristics for identifying expressive performances based on note onset deviations, is particularly relevant for understanding expressive timing.

4.4.2. Methodologies for Creating/Annotating Specialized Datasets for Beat-Aware Expressive Singing

Addressing the critical data scarcity gap identified in 1 (Sec 4.4) and Sec 2.4 of this plan, a significant effort will be dedicated to creating or annotating a specialized dataset.



* **Core Requirement:** The dataset must contain sung vocal performances meticulously aligned with:
    1. Lyrics and corresponding phoneme/note timings.
    2. Expressive vocal parameters (e.g., detailed pitch contours, dynamics/intensity variations, articulation details).
    3. High-resolution beat, downbeat, and tempo information derived from the accompanying music or a reference rhythmic track.
* **Annotation Process and Tooling:**
    * **Source Material:** Start with existing multitrack recordings where clean vocal tracks are available separately from their accompaniment. Alternatively, commission new recordings specifically for this purpose.
    * **Beat Annotation:** Use robust beat tracking algorithms (validated in Phase 1) on the accompaniment tracks, followed by manual verification and correction using tools like Sonic Visualiser <sup>91</sup> or ELAN. The process described in <sup>91</sup> involving iterative tapping, listening with clicks, and waveform-guided adjustment will be adopted.
    * **Vocal Annotation:** Employ established SVS data annotation pipelines for phoneme and note alignment on the isolated vocal tracks. This typically involves Automatic Speech Recognition (ASR) followed by forced alignment tools like the Montreal Forced Aligner (MFA).<sup>110</sup> For pitch (F0) contours, methods like PYin combined with smoothing algorithms (e.g., Smart-Median smoother as used in Annotated-VocalSet <sup>92</sup>) will be used.
    * **Synchronization of Annotations:** A crucial and non-trivial step will be to precisely synchronize the vocal performance annotations (phoneme timings, pitch contours) with the beat annotations derived from the accompaniment. This may require developing custom tools or scripts to align these disparate annotation streams based on shared temporal anchors.
    * **Expressive Parameter Extraction:** Develop methods to quantify expressive vocal parameters relative to the beat structure. This could include measuring micro-timing deviations of sung notes from the metronomic grid, variations in vocal intensity aligned with beat strength, or characterizing articulation patterns (e.g., staccato, legato) in relation to rhythmic figures.
* This focused dataset creation directly addresses the bottleneck highlighted in <sup>1</sup> (Sec 4.4), providing the necessary data to train the LLM for nuanced rhythmic interpretation and to evaluate the system's expressive capabilities. General MIR dataset creation and annotation practices <sup>91</sup> will inform this process. The challenges of annotation precision and time consumption noted in <sup>91</sup> are acknowledged, and resources will be allocated accordingly.

4.4.3. Data Augmentation Techniques

To expand the effective size of available training data, especially the specialized beat-aware expressive singing dataset, data augmentation techniques will be employed, informed by approaches like SingAug 111 and general audio augmentation methods.112



* **For SVS Model Robustness:**
    * **Pitch Augmentation:** Systematically shift the pitch of existing vocal recordings (and corresponding score information) by semitones to create more training exemplars across different keys, as proposed in SingAug.<sup>111</sup>
    * **Mix-up Augmentation:** Interpolate between pairs of training samples (both input features and target acoustic features) to create new synthetic samples, a technique also explored in SingAug for SVS.<sup>111</sup>
    * **Cycle-Consistent Training:** If using augmentation methods that might introduce artifacts (e.g., from vocoding during pitch shifting), a cycle-consistent training strategy, as detailed in SingAug <sup>111</sup>, will be considered to stabilize training and make the SVS model more robust to such noise.
* **For LLM Rhythmic Training:**
    * **Rhythmic Variation Synthesis:** Generate variations of existing sung performances by programmatically altering their rhythmic interpretation while keeping them aligned to a common beat track. This could involve applying different swing ratios, systematically shifting note onsets to create "pushed" or "laid-back" feels, or modifying note durations to simulate different articulations. Techniques like time-stretching and pitch-shifting <sup>112</sup> can be used to create these rhythmic variants.
    * **Noise Injection:** Adding small amounts of controlled noise to beat timings or lyrical inputs to improve the LLM's robustness to imperfections in real-world data.

4.4.4. Few-Shot Learning Approaches

Given the potential cost and time involved in creating large-scale specialized datasets, few-shot learning techniques 113 will be investigated as a complementary strategy, particularly for adapting pre-trained models.



* **For LLM Adaptation:** A large, pre-trained music or language LLM could be fine-tuned on a relatively small set of high-quality examples of beat-aware expressive singing (from the dataset created in 4.4.2). The goal would be to leverage the LLM's existing extensive knowledge and adapt it to the specific nuances of rhythmic interpretation for singing with minimal task-specific data.
* **For SVS Model Adaptation:** Base SVS models known for their few-shot capabilities, such as GPT-SoVITS (renowned for few-shot voice cloning <sup>1</sup>) or MiniMax-Speech (which also supports zero-shot and one-shot cloning <sup>51</sup>), could be adapted using a limited number of examples demonstrating singing with specific rhythmic styles or precise beat-aligned expressivity. This could involve providing reference audio that exemplifies the desired rhythmic performance.

The quality and richness of the training data, particularly the specialized dataset linking beat information to expressive vocal performance, will directly influence the LLM's ability to learn nuanced rhythmic interpretations. This, in turn, is a critical determinant of the perceived musicality and expressiveness of the final synchronized singing output achieved in the live interactive experiments. The effort invested in dataset creation and augmentation is therefore expected to have a high payoff in terms of system performance and the novelty of the research outcomes. The process of creating these specialized datasets might also spur the development of new annotation tools or methodologies for capturing beat-aware expressive singing, offering a secondary contribution to the broader Music Information Retrieval (MIR) and music technology communities, given the complexities highlighted in annotation processes.<sup>91</sup>

**Table 4.4.1: Proposed Experiments Outline**

This table provides a structured overview of the key experiments planned across the research phases, linking them to the core research questions and objectives. It outlines the variables to be manipulated and measured, the general procedures, and the primary metrics for evaluation, ensuring a systematic and rigorous approach to validating the project's hypotheses.


<table>
  <tr>
   <td><strong>Phase</strong>
   </td>
   <td><strong>Experiment Title</strong>
   </td>
   <td><strong>Research Question(s) Addressed</strong>
   </td>
   <td><strong>Key Variables (Independent/Dependent)</strong>
   </td>
   <td><strong>Experimental Setup/Procedure</strong>
   </td>
   <td><strong>Hypotheses</strong>
   </td>
   <td><strong>Data to Collect</strong>
   </td>
   <td><strong>Primary Metrics</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Phase 1: Component Dev. & Offline Validation</strong>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>1A
   </td>
   <td>Beat Tracker Algorithm Comparison
   </td>
   <td>RQ1 (partially)
   </td>
   <td>Ind: Algorithm type, Music genre/complexity. Dep: Accuracy (F1, P-score), Latency.
   </td>
   <td>Evaluate 2-3 beat trackers on standard datasets (GTZAN, etc.) and custom live recordings.
   </td>
   <td>ML-based trackers will outperform traditional ones on complex rhythms. Specific SSL-based vocal beat trackers will show benefits for melodic inputs.
   </td>
   <td>Beat annotations (predicted vs. ground truth), processing times.
   </td>
   <td>F1-score, P-score, Cemgil, Goto <sup>85</sup>, detection latency.
   </td>
  </tr>
  <tr>
   <td>1B
   </td>
   <td>LLM Generation of Rhythmic Common Ground (RCG)
   </td>
   <td>RQ1, RQ3
   </td>
   <td>Ind: LLM architecture, RCG design, Input beat track complexity. Dep: Structural correctness of RCG, Semantic appropriateness.
   </td>
   <td>LLM processes pre-recorded beat tracks & lyrics to generate RCG instances. Offline analysis.
   </td>
   <td>LLMs can generate structurally valid RCGs. Larger/fine-tuned LLMs will produce more musically coherent RCGs.
   </td>
   <td>Generated RCG instances, LLM processing logs.
   </td>
   <td>RCG parsing success rate, % elements correctly timed, expert rating of musical coherence (1-7 Likert).
   </td>
  </tr>
  <tr>
   <td>1C
   </td>
   <td>SVS Responsiveness to RCG/Fine-Grained Control
   </td>
   <td>RQ2 (partially), RQ3
   </td>
   <td>Ind: SVS engine type, RCG complexity/granularity. Dep: Audio quality (MCD), Timing accuracy, Pitch accuracy.
   </td>
   <td>Adapted SVS synthesizes vocals from synthetic RCGs/control signals.
   </td>
   <td>SVS engines with direct parametric control will show better timing accuracy than those requiring score parsing.
   </td>
   <td>Synthesized audio, SVS processing times.
   </td>
   <td>MCD, F0-RMSE, F0-CORR <sup>103</sup>, phoneme/note onset error (ms).
   </td>
  </tr>
  <tr>
   <td><strong>Phase 2: Integrated System & Near Real-Time Testing</strong>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>2A
   </td>
   <td>End-to-End Latency Analysis with Stable Beat Source
   </td>
   <td>RQ2, O1
   </td>
   <td>Ind: System architecture (Hybrid vs. Reactive), Component optimization levels (e.g., TTC for LLM). Dep: End-to-end latency, Component latencies.
   </td>
   <td>Integrated system processes pre-recorded/sequenced beat tracks. Timestamping at all major processing stages.
   </td>
   <td>Hybrid architecture will exhibit lower mean latency than fully reactive LLM. TTC will reduce LLM component latency by >20%.
   </td>
   <td>Latency logs (beat detection, LLM processing, SVS rendering, audio output).
   </td>
   <td>Mean, median, 90th percentile end-to-end latency (ms).
   </td>
  </tr>
  <tr>
   <td>2B
   </td>
   <td>Synchronization Accuracy with Stable Beat Source
   </td>
   <td>RQ2, O2
   </td>
   <td>Ind: System architecture, Synchronization logic parameters. Dep: Beat alignment error.
   </td>
   <td>Integrated system synthesizes vocals to stable beat tracks. Compare SVS output timing to ground truth beat.
   </td>
   <td>System will achieve &lt; ±20ms mean beat alignment error for stable beats.
   </td>
   <td>Synthesized audio, ground truth beat times, predicted vocal event times.
   </td>
   <td>Mean Absolute Synchronization Error (ms), % notes within ±20ms of beat.
   </td>
  </tr>
  <tr>
   <td><strong>Phase 3: Live Beat Sync & Interactive Performance</strong>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>3A
   </td>
   <td>Live Synchronization with Human Percussionist
   </td>
   <td>RQ1, RQ2, RQ4, RQ5, O1, O2, O4
   </td>
   <td>Ind: Percussionist style (e.g., tight vs. swung), Tempo range. Dep: Synchronization accuracy, System stability, Perceived interactivity.
   </td>
   <td>Musician plays live percussion. System generates vocals. Record all audio streams and system logs. Subjective evaluation by musician and listeners.
   </td>
   <td>System will maintain synchronization (e.g., &lt; ±50ms error) for moderately complex live rhythms. LLM-driven expressive timing will be rated as more musical than metronomic.
   </td>
   <td>Live percussion audio, SVS output audio, system logs, musician feedback (questionnaires, interviews), listener ratings.
   </td>
   <td>Objective: Sync error (ms), Latency (ms). Subjective: MOS-Musicality, MOS-Synchronization, MOS-Interactivity (1-7 Likert).<sup>106</sup>
   </td>
  </tr>
  <tr>
   <td>3B
   </td>
   <td>Evaluation of Expressive Rhythmic Performance
   </td>
   <td>RQ5, O4
   </td>
   <td>Ind: LLM expressive control strategy, Type of live beat (e.g., straight vs. shuffle). Dep: Perceived expressiveness, Appropriateness of rhythmic interpretation.
   </td>
   <td>System generates vocals to live beats with different LLM-driven expressive settings. Expert listeners evaluate.
   </td>
   <td>LLM-generated expressive variations (e.g., micro-timing) will be preferred over non-expressive (metronomic) output for specific musical styles.
   </td>
   <td>SVS output audio, expert listener ratings and comments.
   </td>
   <td>Comparative MOS for expressiveness, qualitative analysis of expert feedback.
   </td>
  </tr>
</table>



## **5. Evaluation Strategy and Metrics**

A comprehensive evaluation strategy is essential to rigorously assess the performance of the developed LLM-controlled beat-synchronized SVS system. This strategy will combine objective technical metrics with subjective perceptual evaluations to provide a holistic understanding of the system's capabilities and limitations. The evaluation will be benchmarked against existing systems or baseline approaches where feasible.


### **5.1. Objective Technical Metrics**

Quantitative measurements will be used to assess the system's technical performance across several key dimensions:



* **Latency:** This is a critical factor for any real-time interactive system.<sup>1</sup>
    * **End-to-End Latency:** Measured as the time elapsed from the detection of a live audio beat event by the beat tracking module to the corresponding audible output from the SVS module. This is the most crucial latency metric for perceived interactivity. Target values will be informed by perceptual thresholds discussed in psychoacoustic literature (e.g., aiming for &lt;100ms as suggested by <sup>11</sup>).
    * **Component-Wise Latency:** The processing time of individual modules (beat tracker, LLM inference, SVS rendering) will be measured to identify bottlenecks. Techniques like timestamping data packets at the entry and exit of each module will be employed.
    * Latency reduction due to optimization techniques like Test-Time Compute (TTC) for the LLM <sup>27</sup> or efficient SVS architectures like CSSinger <sup>79</sup> will be quantified.
* **Synchronization Accuracy:** These metrics will quantify how precisely the synthesized vocal events align with the target beats.
    * **Beat Alignment Error:** Calculated as the temporal difference between the detected beat timestamp and the onset of the corresponding synthesized vocal event (e.g., the acoustic onset of a target syllable or note). Mean absolute error and distribution of errors will be reported.
    * **Phoneme-to-Beat Precision:** For systems where the LLM specifies phoneme timings relative to beat subdivisions, this metric will assess how accurately the SVS module renders these phoneme boundaries. This is inspired by the need for precise alignment in SVS data pipelines.<sup>110</sup>
    * **Beat Tracking-Adapted Metrics:** Standard metrics from the beat tracking literature, such as F-measure, P-score, Cemgil score, and Goto score <sup>85</sup>, will be adapted to evaluate the alignment of the synthesized vocal onsets with the ground truth (or detected) beat locations.
* **SVS Quality (Objective):** Standard objective metrics will be used to assess the acoustic quality of the synthesized singing voice, ensuring that efforts to achieve synchronization and expressivity do not unduly degrade vocal quality. The VERSA toolkit <sup>103</sup> provides a comprehensive suite of such metrics.
    * **Mel Cepstral Distortion (MCD):** Measures the spectral distance between the synthesized output and, if available for specific tests, a reference natural singing voice. Lower values indicate better spectral similarity.
    * **F0 Root Mean Square Error (F0-RMSE):** Quantifies the accuracy of the fundamental frequency (pitch) contour.
    * **F0 Correlation (F0-CORR):** Measures the similarity of the synthesized pitch contour to a target contour.
    * **Voicing Decision Error Rate (VDER):** Assesses the accuracy of voiced/unvoiced classifications in the synthesized speech.
    * **SingMOS/SHEET-SSQA:** Objective estimators of subjective MOS scores for singing voice quality.<sup>103</sup>
* **Control Granularity and Responsiveness:** Developing novel metrics in this area will be part of the research, as standard metrics are lacking.
    * **Rhythmic Variation Enactment Accuracy:** Quantify the system's ability to accurately realize fine-grained rhythmic variations (e.g., specific micro-timing shifts, dynamic changes on designated beats) instructed by the LLM via the Rhythmic Common Ground. This involves comparing the LLM's intended rhythmic output (as encoded in the IR) with the actual acoustic realization by the SVS. This is informed by work on quantifying control in generative music systems.<sup>49</sup>
    * **Control Signal Response Time:** Measure the delay between the LLM issuing a new control signal (e.g., a change in rhythmic style) and the SVS output reflecting that change.


### **5.2. Subjective Perceptual Evaluation**

Subjective evaluations by human listeners are indispensable for assessing the musical and interactive qualities of the system, as objective metrics alone cannot capture the full perceptual experience.<sup>115</sup>



* **Musicality and Expressiveness:**
    * Listeners (both expert and naive) will rate the perceived musicality, naturalness, and emotional expressiveness of the synthesized singing performances.
    * Likert scales (typically 1-7 points) will be used for specific attributes such as rhythmic feel (e.g., "how groovy is the performance?"), appropriateness of vocal technique, and emotional congruity with lyrics/beat. Methodologies will draw from established practices in AI music evaluation surveys.<sup>115</sup>
* **Naturalness of Beat Synchronization:**
    * Listeners will rate how well the synthesized singing appears to synchronize with the accompanying live beat.
    * Crucially, the *naturalness* of this synchronization will be assessed – does it sound musically integrated, or robotic and overly rigid? This involves evaluating not just precision but also the musicality of the alignment. Perceptual studies on rhythmic synchronization <sup>18</sup> can inform the design of these listening tests.
* **User Experience in Interactive Scenarios (Musician and Listener Perspectives):**
    * **For Musicians Interacting with the System:** Structured interviews and questionnaires will be used to evaluate their experience. Key dimensions include perceived responsiveness of the AI vocalist, predictability of its behavior, controllability over its performance, and its potential as a creative partner (co-creativity). Evaluation frameworks from NIME and ICMC communities <sup>105</sup> will be adapted for this purpose.
    * **For Audiences Observing Human-AI Performances:** Listeners will rate their engagement with the performance, the perceived interactivity between the human musician and the AI vocalist, and the overall aesthetic quality of the collaborative musical output.
* **Musical Turing Tests:**
    * In controlled experiments, listeners will be presented with short musical excerpts featuring either the LLM-controlled SVS system or a human vocalist performing with a similar backing track. They will be asked to identify which performance is AI-generated. Success rates will provide an indication of the system's ability to achieve human-like musicality and synchronization.<sup>115</sup>
* **Consideration of Criteria Drift:** When designing and conducting subjective evaluations, the phenomenon of "criteria drift" <sup>128</sup> will be taken into account. This refers to the tendency for evaluators' internal standards and criteria to shift as they are exposed to more examples of AI-generated content. To mitigate this, evaluation sessions may be structured with clear initial guidelines, interspersed with calibration stimuli, or employ iterative evaluation designs where criteria can be refined based on initial rounds of feedback.

**Table 5.2.1: Comprehensive Evaluation Metrics**

This table provides a structured overview of the metrics that will be employed, linking them to the research objectives and justifying their selection. It ensures a holistic and rigorous evaluation strategy.


<table>
  <tr>
   <td><strong>Metric Category</strong>
   </td>
   <td><strong>Specific Metric</strong>
   </td>
   <td><strong>Definition</strong>
   </td>
   <td><strong>Unit of Measurement</strong>
   </td>
   <td><strong>Relevance to Research Objective(s)</strong>
   </td>
   <td><strong>Source/Inspiration</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Objective Technical Metrics</strong>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Latency
   </td>
   <td>End-to-End Latency
   </td>
   <td>Time from live beat detection to audible SVS output.
   </td>
   <td>Milliseconds (ms)
   </td>
   <td>O1, O2
   </td>
   <td><sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>Latency
   </td>
   <td>LLM Inference Latency
   </td>
   <td>Time taken for LLM to process input and generate control signals.
   </td>
   <td>Milliseconds (ms)
   </td>
   <td>O1, O2
   </td>
   <td><sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>Latency
   </td>
   <td>SVS Rendering Latency
   </td>
   <td>Time taken for SVS to synthesize audio from control signals.
   </td>
   <td>Milliseconds (ms)
   </td>
   <td>O1
   </td>
   <td><sup>1</sup>
   </td>
  </tr>
  <tr>
   <td>Synchronization Accuracy
   </td>
   <td>Beat Alignment Error
   </td>
   <td>Temporal difference between target beat and synthesized vocal event onset.
   </td>
   <td>Milliseconds (ms)
   </td>
   <td>O2, O4
   </td>
   <td>Adapted from beat tracking <sup>85</sup>
   </td>
  </tr>
  <tr>
   <td>Synchronization Accuracy
   </td>
   <td>F-measure (for vocal onsets vs. beats)
   </td>
   <td>Harmonic mean of precision and recall for aligning vocal onsets to beats within a tolerance window.
   </td>
   <td>Score (0-1)
   </td>
   <td>O2
   </td>
   <td><sup>85</sup>
   </td>
  </tr>
  <tr>
   <td>SVS Quality
   </td>
   <td>MCD (Mel Cepstral Distortion)
   </td>
   <td>Spectral distortion between synthesized and reference audio.
   </td>
   <td>Decibels (dB)
   </td>
   <td>O1, O5
   </td>
   <td><sup>103</sup> (VERSA)
   </td>
  </tr>
  <tr>
   <td>SVS Quality
   </td>
   <td>F0-RMSE (Pitch Accuracy)
   </td>
   <td>Root mean square error of fundamental frequency.
   </td>
   <td>Hertz (Hz) or Cents
   </td>
   <td>O2, O4, O5
   </td>
   <td><sup>103</sup> (VERSA)
   </td>
  </tr>
  <tr>
   <td>SVS Quality
   </td>
   <td>F0-CORR (Pitch Correlation)
   </td>
   <td>Correlation of F0 contours.
   </td>
   <td>Score (-1 to 1)
   </td>
   <td>O2, O4, O5
   </td>
   <td><sup>103</sup> (VERSA)
   </td>
  </tr>
  <tr>
   <td>SVS Quality
   </td>
   <td>SingMOS (Objective MOS)
   </td>
   <td>Predicted Mean Opinion Score for singing voice quality.
   </td>
   <td>Score (e.g., 1-5)
   </td>
   <td>O5
   </td>
   <td><sup>103</sup> (VERSA)
   </td>
  </tr>
  <tr>
   <td>Control & Expressivity
   </td>
   <td>Rhythmic Variation Enactment Error
   </td>
   <td>Difference between LLM-intended rhythmic variation and SVS-rendered variation.
   </td>
   <td>Varies (e.g., ms for timing, dB for dynamics)
   </td>
   <td>O3, O4
   </td>
   <td>Novel metric to be developed; inspired by <sup>119</sup>
   </td>
  </tr>
  <tr>
   <td><strong>Subjective Perceptual Evaluation</strong>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Overall Quality
   </td>
   <td>MOS - Musicality
   </td>
   <td>Listener rating of overall musical quality and appeal.
   </td>
   <td>1-7 Likert Scale
   </td>
   <td>O4, O5
   </td>
   <td><sup>115</sup>
   </td>
  </tr>
  <tr>
   <td>Overall Quality
   </td>
   <td>MOS - Naturalness
   </td>
   <td>Listener rating of the naturalness of the synthesized singing.
   </td>
   <td>1-7 Likert Scale
   </td>
   <td>O5
   </td>
   <td><sup>115</sup>
   </td>
  </tr>
  <tr>
   <td>Synchronization
   </td>
   <td>MOS - Perceived Synchronization
   </td>
   <td>Listener rating of how well singing aligns with the beat.
   </td>
   <td>1-7 Likert Scale
   </td>
   <td>O2, O5
   </td>
   <td>New metric, inspired by <sup>18</sup>
   </td>
  </tr>
  <tr>
   <td>Synchronization
   </td>
   <td>MOS - Naturalness of Synchronization
   </td>
   <td>Listener rating of how musically natural the synchronization feels.
   </td>
   <td>1-7 Likert Scale
   </td>
   <td>O2, O4, O5
   </td>
   <td>New metric
   </td>
  </tr>
  <tr>
   <td>Expressivity
   </td>
   <td>MOS - Rhythmic Expressiveness
   </td>
   <td>Listener rating of the appropriateness and effectiveness of rhythmic variations.
   </td>
   <td>1-7 Likert Scale
   </td>
   <td>O4, O5
   </td>
   <td><sup>115</sup>
   </td>
  </tr>
  <tr>
   <td>Expressivity
   </td>
   <td>MOS - Emotional Congruity
   </td>
   <td>Listener rating of how well vocal emotion matches lyrics/beat character.
   </td>
   <td>1-7 Likert Scale
   </td>
   <td>O4, O5
   </td>
   <td><sup>115</sup>
   </td>
  </tr>
  <tr>
   <td>Interactivity (Musician)
   </td>
   <td>Perceived Responsiveness
   </td>
   <td>Musician's rating of how well the system responds to their live input.
   </td>
   <td>1-7 Likert Scale
   </td>
   <td>O1, O2, O5
   </td>
   <td><sup>106</sup> (NIME frameworks)
   </td>
  </tr>
  <tr>
   <td>Interactivity (Musician)
   </td>
   <td>Creative Partnership Score
   </td>
   <td>Musician's rating of the system as a co-creative partner.
   </td>
   <td>1-7 Likert Scale
   </td>
   <td>O4, O5
   </td>
   <td><sup>106</sup> (NIME frameworks)
   </td>
  </tr>
  <tr>
   <td>Turing Test
   </td>
   <td>AI Detection Rate
   </td>
   <td>Percentage of times listeners correctly identify AI-generated vs. human performance.
   </td>
   <td>Percentage (%)
   </td>
   <td>O5
   </td>
   <td><sup>115</sup>
   </td>
  </tr>
</table>



### **5.3. Benchmarking Against Existing Systems or Baseline Approaches**

To contextualize the performance of the developed system, it will be benchmarked against several baselines:



1. **Non-Real-Time SVS Baseline:** Synthesize the same lyrical content using a high-quality, non-real-time SVS system (e.g., DiffSinger, NNSVS) driven by meticulously crafted, perfectly beat-aligned musical scores. This baseline will represent an upper bound for achievable vocal quality and precise (though potentially rigid) synchronization, without the constraints of real-time LLM control.
2. **Rule-Based Synchronization Baseline:** Implement a simpler synchronization method where lyrical syllables are aligned to beats using basic rules (e.g., aligning stressed syllables to strong beats, distributing remaining syllables evenly) without LLM-driven interpretation or expressive timing. This will help quantify the added value of the LLM's rhythmic intelligence.
3. **"No Beat Sync" Baseline:** The SVS system generates vocals based on lyrics and default SVS timings, without any attempt to synchronize with an external beat. This will highlight the impact of the synchronization mechanisms.
4. **Comparison with Existing Research (Qualitative):** Where possible, qualitatively compare the system's capabilities (e.g., latency, types of expressive control) with those reported in relevant literature for systems like CSSinger <sup>79</sup>, Tungnaá <sup>26</sup>, or LLM-based music generation systems that discuss real-time aspects. Direct quantitative comparison may be challenging due to differences in implementation, hardware, and specific task definitions.
5. **"Wizard of Oz" Experiment (Exploratory):** As an exploratory benchmark for interactivity, a "Wizard of Oz" setup could be considered. In this setup, a human operator manually adjusts SVS parameters in real-time to synchronize with a live beat, simulating an "ideal" intelligent controller. This could provide insights into the upper bounds of perceived interactivity and responsiveness.

The evaluation strategy emphasizes that while objective metrics are vital for validating the technical aspects of the system (such as latency and basic synchronization accuracy), the ultimate success of a *musical* system like the one proposed will be determined by subjective human perception.<sup>115</sup> Musicality, expressiveness, and engagement are inherently subjective qualities. Therefore, robust and well-designed subjective listening tests and interactive evaluations will form a cornerstone of the assessment process. A particular challenge lies in objectively quantifying nuanced rhythmic interpretations like "swing" or "groove".<sup>1</sup> Standard synchronization metrics typically measure deviation from a rigid metronomic grid, whereas musical "feel" often involves systematic and intentional deviations from this grid, as seen in analyses of expressive MIDI performance.<sup>9</sup> This points to a need for developing novel objective metrics for rhythmic feel or relying heavily on expert subjective assessment for these more nuanced aspects of performance.

There is a hypothesized causal link between the objectively measurable control granularity of the system (Sec 5.1) and the subjectively perceived expressiveness and interactivity (Sec 5.2). If the system is incapable of enacting fine-grained rhythmic changes as dictated by the LLM, its expressive potential will inherently be limited, as musical expression often arises from subtle variations in timing and dynamics. Finally, the evaluation of a truly interactive, co-creative AI music system may necessitate new paradigms that go beyond traditional SVS or MIR evaluation methodologies. Frameworks and approaches from HCI and NIME research <sup>105</sup>, which focus on user experience and interaction quality, become highly relevant in this context, as the system is not merely generating audio but is intended to interact musically.


## **6. Expected Outcomes, Contributions, and Dissemination Plan**

This research is poised to deliver several significant outcomes and contributions to the fields of AI, music technology, and human-computer interaction. The dissemination plan aims to share these findings broadly with relevant scientific and artistic communities.


### **6.1. Novel Algorithms, Models, or Architectural Frameworks**



* **Validated Architectural Framework:** The primary outcome will be at least one, and potentially two, comprehensively evaluated architectural frameworks for LLM-controlled, real-time, beat-synchronized SVS. This will include detailed specifications of module interactions, data flow, and control mechanisms, particularly for the proposed hybrid architecture.
* **LLM-based Rhythmic Interpretation Algorithms:** Novel algorithms or fine-tuned LLM models capable of interpreting live beat information and translating it into musically coherent and rhythmically precise control signals for SVS. This includes methods for the LLM to understand and generate expressive timing variations.
* **"Rhythmic Common Ground" Representation:** A formal proposal and prototype of an intermediate representation designed for efficient and expressive communication of rhythmic intent between LLMs and SVS systems in real-time.
* **Adapted SVS Models:** One or more existing open-source SVS models will be adapted and optimized to accept fine-grained, real-time rhythmic control signals, enhancing their suitability for interactive musical applications.


### **6.2. Publicly Available Datasets, Software, or Tools**

In line with the open research ethos prevalent in the AI and MIR communities <sup>1</sup>, the following resources are planned for public release, contingent on licensing permissions of underlying components:



* **Specialized Annotated Dataset:** If the creation of a new dataset for beat-aware expressive singing (as outlined in Sec 4.4.2) proves successful and yields data of sufficient quality and utility, it will be curated and made available to the research community. This would address a significant data scarcity issue.<sup>1</sup>
* **Open-Source Software Modules:** Key software components developed during the research, such as specific beat tracker adaptations, LLM control scripts, SVS interface layers, the Rhythmic Common Ground parser/generator, and synchronization logic, will be released under appropriate open-source licenses (e.g., MIT, Apache 2.0).
* **Evaluation Toolkit Components:** Scripts, methodologies, and potentially new objective metrics developed for evaluating beat-synchronized SVS systems could be packaged into a toolkit or contributed to existing evaluation frameworks like VERSA.<sup>103</sup>


### **6.3. Scientific Publications and Conference Presentations**

The findings of this research will be disseminated through peer-reviewed publications and presentations at high-impact international conferences and journals. Target venues include:



* **Core AI/Machine Learning & Signal Processing:**
    * IEEE International Conference on Acoustics, Speech, and Signal Processing (ICASSP)
    * IEEE/ACM Transactions on Audio, Speech, and Language Processing (TASLP)
    * Neural Information Processing Systems (NeurIPS)
    * International Conference on Machine Learning (ICML)
* **Music Technology & Music Information Retrieval (MIR):**
    * International Society for Music Information Retrieval Conference (ISMIR)
    * International Computer Music Conference (ICMC)
    * Conference on New Interfaces for Musical Expression (NIME)
    * Journal of New Music Research
    * Computer Music Journal
* **AI & Creativity / Human-Computer Interaction:**
    * Relevant conferences and journals focusing on AI and the Arts, or Human-AI Interaction.

A minimum of two to three peer-reviewed journal articles and three to four conference papers are anticipated over the course of the project.


### **6.4. Broader Impact on AI Music, Human-Computer Interaction, and Digital Arts**

The research is expected to have a wide-ranging impact:



* **Advancing AI in Music:** It will push the boundaries of how AI can be used in music, moving beyond offline generation towards real-time, interactive performance capabilities.<sup>1</sup> This contributes to the development of more musically intelligent and responsive AI systems.
* **New Tools for Creatives:** The outcomes could lead to new tools for musicians, composers, vocalists, and performers, enabling novel forms of expression and collaboration with AI.<sup>1</sup> This includes applications in live performance, studio production, and interactive installations.
* **Informing Human-AI Co-Creation:** The study of how humans interact with an AI vocalist that responds to their live rhythmic input will provide valuable insights into the design of future human-AI co-creative systems across various artistic domains.
* **Educational Applications:** Such technology could potentially be used in music education, for instance, to provide students with an AI practice partner that can sing along in time.

The research aims not only to produce a functional system but also to contribute a deeper understanding of how LLMs can effectively process and generate musical rhythm, and how SVS technology can be dynamically controlled for enhanced musical expressivity in real-time contexts. This dual contribution—a tangible system and fundamental knowledge—is a key expected outcome. While the democratization of expressive vocal tools is a positive potential impact <sup>1</sup>, it is also important to consider and discuss the broader societal implications, such as the potential for skill devaluation for human performers.<sup>1</sup> The dissemination strategy will aim to foster a balanced discussion on these aspects.


## **7. Ethical Considerations and Risk Management**

The development and deployment of AI systems, particularly those involving voice and creative content, necessitate careful consideration of ethical implications and potential risks. This research will proactively address these concerns.


### **7.1. Voice Cloning and Artist Rights**

As noted in <sup>1</sup> (Sec 6.4), the use of voice cloning technologies, such as those available in SVS models like GPT-SoVITS <sup>1</sup> or MiniMax-Speech <sup>52</sup>, raises significant ethical issues concerning artist rights and identity.



* **Risk:** Unauthorized creation of singing voices that mimic existing artists, leading to potential misuse, misrepresentation, or economic harm to the artists.
* **Mitigation:**
    * **Consent:** If any voice cloning capabilities are used for creating specific voice identities (beyond generic voices), explicit, informed consent will be obtained from all voice donors. The purpose and extent of voice use will be clearly communicated.
    * **Ethical Sourcing:** Prioritize the use of ethically sourced voice datasets where consent for research and synthesis is already established, or use synthesized voices that are not directly attributable to specific, identifiable individuals for public demonstrations and publications.
    * **Policy Development:** Develop internal guidelines for the responsible use of any cloned voices generated during the research, strictly prohibiting their use for deceptive purposes or unauthorized commercial exploitation.
    * **Watermarking (Exploratory):** Investigate the feasibility of embedding imperceptible watermarks in the synthesized audio to trace its origin, should this become relevant for specific applications.


### **7.2. Copyright of AI-Generated Musical Content**

The generation of novel musical phrases and vocal performances by an LLM-SVS system brings to the fore complex questions of authorship and copyright.<sup>1</sup>



* **Risk:** The system might inadvertently generate melodies or vocal expressions that are substantially similar to existing copyrighted works, especially if trained on copyrighted material. Ambiguity regarding the ownership of AI-generated musical elements could also arise.
* **Mitigation:**
    * **Training Data Scrutiny:** To the extent feasible, prioritize the use of public domain or permissively licensed musical data (lyrics, melodies if used for conditioning) for training and fine-tuning the LLM and SVS components. Where copyrighted material is used under fair use or research exceptions, its influence on generated output will be carefully considered.
    * **Originality Focus:** Design the system and prompts to encourage the generation of novel musical material rather than simple reproduction of training data.
    * **Transparency:** Clearly acknowledge the AI-assisted nature of any generated musical content. In research outputs, provide details about the models and data used.
    * **Legal Consultation:** If the research moves towards applications with commercial potential, consult with legal experts on copyright implications for AI-generated music.


### **7.3. Data Privacy in Dataset Creation and User Studies**

The collection of new datasets (Sec 4.4.2) or conducting user studies for subjective evaluation (Sec 5.2) may involve personal data.



* **Risk:** Accidental disclosure or misuse of personal data from voice donors or evaluation participants. Collection of sensitive information without adequate consent.
* **Mitigation:**
    * **Anonymization/Pseudonymization:** All data collected from human participants in evaluation studies (e.g., questionnaire responses, demographic information) will be anonymized or pseudonymized at the earliest possible stage.
    * **Informed Consent:** Participants in any study involving data collection will be provided with clear information about how their data will be used, stored, and protected, and will provide informed consent before participation.
    * **Data Security:** Implement robust data security measures for storing and handling any personal or sensitive data, in compliance with relevant data protection regulations (e.g., GDPR, CCPA).
    * **Ethical Review Board (IRB) Approval:** Seek approval from an institutional ethical review board before commencing any human subject research, including dataset creation involving new recordings of individuals or user evaluation studies.


### **7.4. Mitigation Strategies for Identified Risks (General)**



* **Bias in AI Models:**
    * **Risk:** The LLM's rhythmic interpretations or the SVS model's vocal characteristics might exhibit biases (e.g., cultural, stylistic, gender) learned from unbalanced or unrepresentative training data. This could lead to stereotypical or limited expressive outputs. <sup>1</sup> (Sec 6.4) mentions the importance of transparency.
    * **Mitigation:** Actively seek diverse datasets for training and fine-tuning, covering a range of musical styles, cultural origins, and vocal types. Implement bias detection and mitigation techniques during model development and evaluation where possible. Ensure transparency about the limitations of the training data.
* **Potential for Misuse (Deepfakes, Disinformation):**
    * **Risk:** Advanced voice synthesis technology could potentially be misused for creating deceptive audio content (e.g., "deepfake" singing).
    * **Mitigation:** While this research focuses on musical applications, the potential for misuse will be acknowledged. Publicly released models or tools will be accompanied by clear ethical guidelines and statements regarding responsible use. Focus research dissemination on creative and assistive applications.
* **Technical Failures and Robustness:**
    * **Risk:** The system may fail or produce undesirable output in complex live environments (e.g., noisy conditions, highly erratic beat input).
    * **Mitigation:** Rigorous testing under diverse conditions (Phase 3 experiments). Implement robust error handling and fallback mechanisms within the system architecture. Clearly define the operational limits of the system.

Addressing these ethical considerations proactively is not merely a compliance exercise but an essential component of responsible innovation. It fosters public trust, encourages wider adoption of beneficial AI technologies, and helps navigate the societal impact of increasingly sophisticated AI capabilities in creative domains. As AI-generated singing becomes more advanced, this research will inevitably contribute to the ongoing discourse about "authenticity" in music and performance <sup>1</sup>, and it is important to frame these contributions within a strong ethical framework.


## **8. Conclusion**

The endeavor to create an LLM-controlled real-time singing voice synthesis system capable of precise and expressive synchronization with a live audio beat represents a significant and exciting challenge at the vanguard of AI and digital music technology. This research plan outlines a systematic and scientifically rigorous approach to tackling this multifaceted problem. By leveraging recent advancements in Large Language Models, adapting state-of-the-art Singing Voice Synthesis technologies, and pioneering novel solutions for rhythmic interpretation and real-time control, this project aims to make substantial contributions to the field.

The core of the proposed research involves a multi-phase development and evaluation strategy, beginning with the offline validation of individual system components—including advanced beat tracking, LLM-based rhythmic interpretation, and responsive SVS modules. A key innovation will be the development of a "Rhythmic Common Ground," an intermediate representation designed to facilitate nuanced and efficient communication of timing and expressive intent between the LLM and the SVS engine. The project will then progress to the integration of these components into a cohesive system, with a strong emphasis on minimizing end-to-end latency and ensuring robust synchronization. The ultimate validation will occur through interactive performance experiments with live musicians, assessing not only the technical proficiency of the system but also its perceived musicality, expressiveness, and interactivity.

The anticipated outcomes include validated architectural frameworks for real-time LLM-SVS systems, novel algorithms for LLM-driven rhythmic interpretation, the proposed Rhythmic Common Ground representation, and potentially new annotated datasets for beat-aware expressive singing. These contributions are expected to have a broader impact, paving the way for more musically intelligent and interactive AI systems, providing innovative tools for musicians and creators, and deepening our understanding of how complex cognitive and artistic tasks like musical performance can be modeled and realized computationally. The research process itself, navigating the intricate challenges of integrating sophisticated AI with the demands of real-time musical interaction, will yield valuable knowledge and insights for the wider scientific community.

While the technical hurdles are considerable—particularly concerning latency, the granularity of control, and data scarcity—the potential rewards in advancing human-AI co-creation in music are immense. By systematically addressing these challenges and adhering to a strong ethical framework, this research aspires to not only develop novel expressive tools but also to contribute to a future where AI can participate more deeply and intuitively in the dynamic and collaborative art of musical performance, potentially shifting current paradigms and opening new horizons for artistic expression.


## **Works Cited**



* The primary source document <sup>1</sup>, "Adapting Open-Source Vocal Synthesis for LLM-Controlled Real-Time Singing with Live Beat Synchronization," underpins much of the background and initial project identification.
* Specific research papers and resources are cited inline using their respective IDs (e.g.<sup>56</sup>). A full bibliography would be compiled based on these cited sources.


#### Works cited



1. LLM Real-Time Singing Adaptation
2. Understanding LLM agent architectures | DataStax, accessed June 1, 2025, [https://www.datastax.com/guides/understanding-llm-agent-architectures?utm_name=Social&utm_source=twitter&utm_medium=Free&utm_term=datastax](https://www.datastax.com/guides/understanding-llm-agent-architectures?utm_name=Social&utm_source=twitter&utm_medium=Free&utm_term=datastax)
3. Awesome-LLM-based-AI-Agents-Knowledge/5-design-patterns.md at main - GitHub, accessed June 1, 2025, [https://github.com/mind-network/Awesome-LLM-based-AI-Agents-Knowledge/blob/main/5-design-patterns.md](https://github.com/mind-network/Awesome-LLM-based-AI-Agents-Knowledge/blob/main/5-design-patterns.md)
4. stepfun-ai/Step-Audio - GitHub, accessed June 1, 2025, [https://github.com/stepfun-ai/Step-Audio](https://github.com/stepfun-ai/Step-Audio)
5. AudioLLMs/Awesome-Audio-LLM: Audio Large Language Models - GitHub, accessed June 1, 2025, [https://github.com/AudioLLMs/Awesome-Audio-LLM](https://github.com/AudioLLMs/Awesome-Audio-LLM)
6. Can Large Language Models Understand Intermediate Representations? - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2502.06854v1](https://arxiv.org/html/2502.06854v1)
7. From Shots to Stories: LLM-Assisted Video Editing with Unified Language Representations, accessed June 1, 2025, [https://arxiv.org/html/2505.12237v1](https://arxiv.org/html/2505.12237v1)
8. AI-Enabled Text-to-Music Generation: A Comprehensive Review of ..., accessed June 1, 2025, [https://www.mdpi.com/2079-9292/14/6/1197](https://www.mdpi.com/2079-9292/14/6/1197)
9. (PDF) The GigaMIDI Dataset with Features for Expressive Music ..., accessed June 1, 2025, [https://www.researchgate.net/publication/388795754_The_GigaMIDI_Dataset_with_Features_for_Expressive_Music_Performance_Detection](https://www.researchgate.net/publication/388795754_The_GigaMIDI_Dataset_with_Features_for_Expressive_Music_Performance_Detection)
10. Journal-Online - AES - Audio Engineering Society, accessed June 1, 2025, [https://aes2.org/journal-online/?vol=69&num=12](https://aes2.org/journal-online/?vol=69&num=12)
11. (PDF) Perceptual thresholds of spatial audio update latency in ..., accessed June 1, 2025, [https://www.researchgate.net/publication/310761977_Perceptual_thresholds_of_spatial_audio_update_latency_in_virtual_auditory_and_audiovisual_environments](https://www.researchgate.net/publication/310761977_Perceptual_thresholds_of_spatial_audio_update_latency_in_virtual_auditory_and_audiovisual_environments)
12. Psychoacoustics - Voyage au centre de l'audition, accessed June 1, 2025, [https://www.cochlea.eu/en/sound/psychoacoustics/](https://www.cochlea.eu/en/sound/psychoacoustics/)
13. Just-noticeable difference - Wikipedia, accessed June 1, 2025, [https://en.wikipedia.org/wiki/Just-noticeable_difference](https://en.wikipedia.org/wiki/Just-noticeable_difference)
14. AES 146TH CONVENTION PROGRAM - Audio Engineering Society, accessed June 1, 2025, [https://www.aes.org/events/146/146thWrapUp.pdf](https://www.aes.org/events/146/146thWrapUp.pdf)
15. 15th International Conference on Music Perception and Cognition 10th triennial conference of the European Society for the Cognit - Uni Graz, accessed June 1, 2025, [https://static.uni-graz.at/fileadmin/veranstaltungen/music-psychology-conference2018/documents/ICMPC15ESCOM10abstractbook.pdf](https://static.uni-graz.at/fileadmin/veranstaltungen/music-psychology-conference2018/documents/ICMPC15ESCOM10abstractbook.pdf)
16. Dysrhythmia: a specific congenital rhythm perception deficit - Frontiers, accessed June 1, 2025, [https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2014.00018/full](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2014.00018/full)
17. Cognitive Crescendo: How Music Shapes the Brain's Structure and Function - PMC, accessed June 1, 2025, [https://pmc.ncbi.nlm.nih.gov/articles/PMC10605363/](https://pmc.ncbi.nlm.nih.gov/articles/PMC10605363/)
18. (PDF) Pitch biases sensorimotor synchronization to auditory rhythms, accessed June 1, 2025, [https://www.researchgate.net/publication/391809448_Pitch_biases_sensorimotor_synchronization_to_auditory_rhythms](https://www.researchgate.net/publication/391809448_Pitch_biases_sensorimotor_synchronization_to_auditory_rhythms)
19. The ability to tap to a beat relates to cognitive, linguistic, and perceptual skills - PMC, accessed June 1, 2025, [https://pmc.ncbi.nlm.nih.gov/articles/PMC3594434/](https://pmc.ncbi.nlm.nih.gov/articles/PMC3594434/)
20. Music Perception | Oxford Research Encyclopedia of Psychology, accessed June 1, 2025, [https://oxfordre.com/psychology/display/10.1093/acrefore/9780190236557.001.0001/acrefore-9780190236557-e-890?d=%2F10.1093%2Facrefore%2F9780190236557.001.0001%2Facrefore-9780190236557-e-890&p=emailAUAQc4sGsP5lk](https://oxfordre.com/psychology/display/10.1093/acrefore/9780190236557.001.0001/acrefore-9780190236557-e-890?d=/10.1093/acrefore/9780190236557.001.0001/acrefore-9780190236557-e-890&p=emailAUAQc4sGsP5lk)
21. There's More to Timing than Time: Investigating Musical Microrhythm Across Disciplines and Cultures, accessed June 1, 2025, [https://online.ucpress.edu/mp/article/41/3/176/199793/There-s-More-to-Timing-than-TimeInvestigating](https://online.ucpress.edu/mp/article/41/3/176/199793/There-s-More-to-Timing-than-TimeInvestigating)
22. arxiv.org, accessed June 1, 2025, [https://arxiv.org/pdf/2408.14340](https://arxiv.org/pdf/2408.14340)
23. Use MPE with software instruments in Logic Pro for Mac - Apple Support (GU), accessed June 1, 2025, [https://support.apple.com/en-gu/guide/logicpro/lgcp8f599497/mac](https://support.apple.com/en-gu/guide/logicpro/lgcp8f599497/mac)
24. (PDF) Comparative Evaluation in the Wild: Systems for the ..., accessed June 1, 2025, [https://www.researchgate.net/publication/381167137_Comparative_evaluation_in_the_wild_Systems_for_the_expressive_rendering_of_music](https://www.researchgate.net/publication/381167137_Comparative_evaluation_in_the_wild_Systems_for_the_expressive_rendering_of_music)
25. The Synergy of Music Theory and AI: Learning Multi-Level Expressive Interpretation, accessed June 1, 2025, [https://ofai.at/papers/oefai-tr-94-06.pdf](https://ofai.at/papers/oefai-tr-94-06.pdf)
26. nime.org, accessed June 1, 2025, [https://nime.org/proceedings/2024/nime2024_78.pdf](https://nime.org/proceedings/2024/nime2024_78.pdf)
27. Scaling Auditory Cognition via Test-Time Compute in Audio Language Models - arXiv, accessed June 1, 2025, [https://arxiv.org/abs/2503.23395](https://arxiv.org/abs/2503.23395)
28. arXiv:2503.23395v1 [cs.SD] 30 Mar 2025, accessed June 1, 2025, [https://arxiv.org/pdf/2503.23395](https://arxiv.org/pdf/2503.23395)
29. An Easy Introduction to LLM Reasoning, AI Agents, and Test Time Scaling, accessed June 1, 2025, [https://developer.nvidia.com/blog/an-easy-introduction-to-llm-reasoning-ai-agents-and-test-time-scaling/](https://developer.nvidia.com/blog/an-easy-introduction-to-llm-reasoning-ai-agents-and-test-time-scaling/)
30. Optimizing speech synthesis for real-time conversational AI interactions - ElevenLabs, accessed June 1, 2025, [https://elevenlabs.io/blog/optimizing-speech-synthesis-for-real-time-conversational-ai-interactions](https://elevenlabs.io/blog/optimizing-speech-synthesis-for-real-time-conversational-ai-interactions)
31. LLMs Meet Multimodal Generation and Editing: A Survey - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2405.19334v1](https://arxiv.org/html/2405.19334v1)
32. Foundation Models for Music: A Survey - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2408.14340v1](https://arxiv.org/html/2408.14340v1)
33. ChatMusician: Understanding and Generating Music Intrinsically with LLM - ResearchGate, accessed June 1, 2025, [https://www.researchgate.net/publication/384209883_ChatMusician_Understanding_and_Generating_Music_Intrinsically_with_LLM](https://www.researchgate.net/publication/384209883_ChatMusician_Understanding_and_Generating_Music_Intrinsically_with_LLM)
34. CrossMuSim: A Cross-Modal Framework for Music Similarity Retrieval with LLM-Powered Text Description Sourcing and Mining - arXiv, accessed June 1, 2025, [https://arxiv.org/pdf/2503.23128](https://arxiv.org/pdf/2503.23128)
35. A Survey on Cross-Modal Interaction Between Music and Multimodal Data - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2504.12796v1](https://arxiv.org/html/2504.12796v1)
36. NotaGen: Advancing Musicality in Symbolic Music Generation with Large Language Model Training Paradigms - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2502.18008v1](https://arxiv.org/html/2502.18008v1)
37. arxiv.org, accessed June 1, 2025, [https://arxiv.org/abs/2503.08638](https://arxiv.org/abs/2503.08638)
38. accessed January 1, 1970, [https://arxiv.org/abs/2405.19334](https://arxiv.org/abs/2405.19334)
39. [2408.14340] Foundation Models for Music: A Survey - arXiv, accessed June 1, 2025, [https://arxiv.org/abs/2408.14340](https://arxiv.org/abs/2408.14340)
40. [Literature Review] Foundation Models for Music: A Survey - Moonlight, accessed June 1, 2025, [https://www.themoonlight.io/en/review/foundation-models-for-music-a-survey](https://www.themoonlight.io/en/review/foundation-models-for-music-a-survey)
41. Paper page - Foundation Models for Music: A Survey, accessed June 1, 2025, [https://huggingface.co/papers/2408.14340](https://huggingface.co/papers/2408.14340)
42. [2504.12796] A Survey on Cross-Modal Interaction Between Music and Multimodal Data, accessed June 1, 2025, [https://arxiv.org/abs/2504.12796](https://arxiv.org/abs/2504.12796)
43. [2503.11190] Cross-Modal Learning for Music-to-Music-Video Description Generation - arXiv, accessed June 1, 2025, [https://arxiv.org/abs/2503.11190](https://arxiv.org/abs/2503.11190)
44. Cross-modal interactions in the perception of musical performance - PubMed, accessed June 1, 2025, [https://pubmed.ncbi.nlm.nih.gov/16289067/](https://pubmed.ncbi.nlm.nih.gov/16289067/)
45. ChatMusician: Understanding and Generating Music Intrinsically with LLM - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2402.16153v1](https://arxiv.org/html/2402.16153v1)
46. arxiv.org, accessed June 1, 2025, [https://arxiv.org/abs/2402.16153](https://arxiv.org/abs/2402.16153)
47. Text2midi: Generating Symbolic Music from Captions - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2412.16526v1](https://arxiv.org/html/2412.16526v1)
48. (PDF) Music Creation Using a Hybrid Model of LLM And LSTM, accessed June 1, 2025, [https://www.researchgate.net/publication/391894666_Music_Creation_Using_a_Hybrid_Model_of_LLM_And_LSTM](https://www.researchgate.net/publication/391894666_Music_Creation_Using_a_Hybrid_Model_of_LLM_And_LSTM)
49. Text2midi-InferAlign: Improving Symbolic Music Generation with Inference-Time Alignment, accessed June 1, 2025, [https://arxiv.org/html/2505.12669v1](https://arxiv.org/html/2505.12669v1)
50. ACE-Step: A Step Towards Music Generation Foundation Model - GitHub, accessed June 1, 2025, [https://github.com/ace-step/ACE-Step](https://github.com/ace-step/ACE-Step)
51. 1 Introduction - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2505.07916v1](https://arxiv.org/html/2505.07916v1)
52. [2505.07916] MiniMax-Speech: Intrinsic Zero-Shot Text-to-Speech with a Learnable Speaker Encoder - arXiv, accessed June 1, 2025, [https://arxiv.org/abs/2505.07916](https://arxiv.org/abs/2505.07916)
53. MiniMax-Speech Tech Report | Intrinsic Zero-Shot Text-to-Speech with a Learnable Speaker Encoder, accessed June 1, 2025, [https://minimax-ai.github.io/tts_tech_report/](https://minimax-ai.github.io/tts_tech_report/)
54. YuE: Scaling Open Foundation Models for Long-Form Music Generation - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2503.08638v1](https://arxiv.org/html/2503.08638v1)
55. Revision History for YuE: Scaling Open Foundation Models, accessed June 1, 2025, [https://openreview.net/revisions?id=ADbl0983tB](https://openreview.net/revisions?id=ADbl0983tB)
56. Prompt-Singer: Controllable Singing-Voice-Synthesis with Natural Language Prompt - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2403.11780v1](https://arxiv.org/html/2403.11780v1)
57. arXiv:2403.11780v3 [cs.SD] 6 Jan 2025, accessed June 1, 2025, [https://arxiv.org/pdf/2403.11780](https://arxiv.org/pdf/2403.11780)
58. arxiv.org, accessed June 1, 2025, [https://arxiv.org/abs/2403.11780](https://arxiv.org/abs/2403.11780)
59. GPT-Sovits V3 TTS (407M) Release - 0-Shot Voice Cloning , Multi Language - Reddit, accessed June 1, 2025, [https://www.reddit.com/r/LocalLLaMA/comments/1jbyg29/gptsovits_v3_tts_407m_release_0shot_voice_cloning/](https://www.reddit.com/r/LocalLLaMA/comments/1jbyg29/gptsovits_v3_tts_407m_release_0shot_voice_cloning/)
60. GPT SoVITS: Unveiling the Revolutionary Open-Source Text-to-Speech - YouTube, accessed June 1, 2025, [https://www.youtube.com/watch?v=PflD7OPI6kw](https://www.youtube.com/watch?v=PflD7OPI6kw)
61. X-T-E-R/GPT-SoVITS-Inference: Inference Specialization - GitHub, accessed June 1, 2025, [https://github.com/X-T-E-R/GPT-SoVITS-Inference](https://github.com/X-T-E-R/GPT-SoVITS-Inference)
62. RVC-Boss/GPT-SoVITS: 1 min voice data can also be used ... - GitHub, accessed June 1, 2025, [https://github.com/RVC-Boss/GPT-SoVITS](https://github.com/RVC-Boss/GPT-SoVITS)
63. huangxu1991/GPT-SoVITS-VC: VC Without Retrain! - GitHub, accessed June 1, 2025, [https://github.com/huangxu1991/GPT-SoVITS-VC](https://github.com/huangxu1991/GPT-SoVITS-VC)
64. Releases · X-T-E-R/GPT-SoVITS-Inference - GitHub, accessed June 1, 2025, [https://github.com/X-T-E-R/GPT-SoVITS-Inference/releases](https://github.com/X-T-E-R/GPT-SoVITS-Inference/releases)
65. 箱庭XTer XTER - GitHub, accessed June 1, 2025, [https://github.com/X-T-E-R](https://github.com/X-T-E-R)
66. NNSVS: A Neural Network-Based Singing Voice Synthesis Toolkit | Request PDF, accessed June 1, 2025, [https://www.researchgate.net/publication/364932523_NNSVS_A_Neural_Network-Based_Singing_Voice_Synthesis_Toolkit](https://www.researchgate.net/publication/364932523_NNSVS_A_Neural_Network-Based_Singing_Voice_Synthesis_Toolkit)
67. Unlock Your Creativity: Build Your Own Singing Voice Synthesizer - Toolify.ai, accessed June 1, 2025, [https://www.toolify.ai/ai-news/unlock-your-creativity-build-your-own-singing-voice-synthesizer-1180787](https://www.toolify.ai/ai-news/unlock-your-creativity-build-your-own-singing-voice-synthesizer-1180787)
68. REST API endpoints for licenses - GitHub Docs, accessed June 1, 2025, [https://docs.github.com/en/rest/licenses/licenses](https://docs.github.com/en/rest/licenses/licenses)
69. NNSVS demos — nnsvs 0.1.0 documentation, accessed June 1, 2025, [https://nnsvs.github.io/notebooks/Demos.html](https://nnsvs.github.io/notebooks/Demos.html)
70. nnsvs/nnsvs: Neural network-based singing voice synthesis ... - GitHub, accessed June 1, 2025, [https://github.com/nnsvs/nnsvs](https://github.com/nnsvs/nnsvs)
71. NNSVS — nnsvs 0.1.0 documentation, accessed June 1, 2025, [https://nnsvs.github.io/](https://nnsvs.github.io/)
72. Emotionally Expressive Speech and Singing Voice Synthesis with Large Language Models via Flow Matching - Preprints.org, accessed June 1, 2025, [https://www.preprints.org/frontend/manuscript/b167f2017789d183833e73ed4fc4f70e/download_pub](https://www.preprints.org/frontend/manuscript/b167f2017789d183833e73ed4fc4f70e/download_pub)
73. DiffRhythm: Blazingly Fast and Embarrassingly Simple End-to-End Full-Length Song Generation with Latent Diffusion - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2503.01183v1](https://arxiv.org/html/2503.01183v1)
74. MoonInTheRiver/DiffSinger: DiffSinger: Singing Voice ... - GitHub, accessed June 1, 2025, [https://github.com/MoonInTheRiver/DiffSinger](https://github.com/MoonInTheRiver/DiffSinger)
75. MIT license - MoonInTheRiver/DiffSinger - GitHub, accessed June 1, 2025, [https://github.com/MoonInTheRiver/DiffSinger/blob/master/LICENSE](https://github.com/MoonInTheRiver/DiffSinger/blob/master/LICENSE)
76. DiffSinger/resources/apply_form.md at master - GitHub, accessed June 1, 2025, [https://github.com/MoonInTheRiver/DiffSinger/blob/master/resources/apply_form.md](https://github.com/MoonInTheRiver/DiffSinger/blob/master/resources/apply_form.md)
77. TCSinger 2: Customizable Multilingual Zero-shot Singing Voice Synthesis - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2505.14910v1](https://arxiv.org/html/2505.14910v1)
78. arxiv.org, accessed June 1, 2025, [https://arxiv.org/abs/2505.14910](https://arxiv.org/abs/2505.14910)
79. ojs.aaai.org, accessed June 1, 2025, [https://ojs.aaai.org/index.php/AAAI/article/download/34541/36696](https://ojs.aaai.org/index.php/AAAI/article/download/34541/36696)
80. arXiv:2504.19062v1 [eess.AS] 27 Apr 2025, accessed June 1, 2025, [https://arxiv.org/pdf/2504.19062](https://arxiv.org/pdf/2504.19062)
81. [2504.19062] Versatile Framework for Song Generation with Prompt-based Control - arXiv, accessed June 1, 2025, [https://arxiv.org/abs/2504.19062](https://arxiv.org/abs/2504.19062)
82. Versatile Framework for Song Generation with Prompt-based Control - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2504.19062v1](https://arxiv.org/html/2504.19062v1)
83. MIT license - cyanbx/Prompt-Singer - GitHub, accessed June 1, 2025, [https://github.com/cyanbx/Prompt-Singer/blob/main/LICENSE](https://github.com/cyanbx/Prompt-Singer/blob/main/LICENSE)
84. Exploring the World of Open-Source Text-to-Speech Models - BentoML, accessed June 1, 2025, [https://www.bentoml.com/blog/exploring-the-world-of-open-source-text-to-speech-models](https://www.bentoml.com/blog/exploring-the-world-of-open-source-text-to-speech-models)
85. archives.ismir.net, accessed June 1, 2025, [https://archives.ismir.net/ismir2022/paper/000074.pdf](https://archives.ismir.net/ismir2022/paper/000074.pdf)
86. SinTechSVS: A Singing Technique Controllable Singing Voice Synthesis System | Request PDF - ResearchGate, accessed June 1, 2025, [https://www.researchgate.net/publication/380197344_SinTechSVS_A_Singing_Technique_Controllable_Singing_Voice_Synthesis_System](https://www.researchgate.net/publication/380197344_SinTechSVS_A_Singing_Technique_Controllable_Singing_Voice_Synthesis_System)
87. LLFM-Voice: Emotionally Expressive Speech and Singing Voice Synthesis with Large Language Models via Flow Matching - Preprints.org, accessed June 1, 2025, [https://www.preprints.org/manuscript/202504.1831/v1](https://www.preprints.org/manuscript/202504.1831/v1)
88. Scaling Auditory Cognition via Test-Time Compute in Audio Language Models - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2503.23395v1](https://arxiv.org/html/2503.23395v1)
89. The GigaMIDI Dataset with Features for Expressive Music Performance Detection - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2502.17726v1](https://arxiv.org/html/2502.17726v1)
90. A Survey on Music Generation from Single-Modal, Cross-Modal and Multi-Modal Perspectives - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2504.00837v2](https://arxiv.org/html/2504.00837v2)
91. How do we annotate? — Tempo, Beat and Downbeat Estimation, accessed June 1, 2025, [https://tempobeatdownbeat.github.io/tutorial/ch2_basics/annotation.html](https://tempobeatdownbeat.github.io/tutorial/ch2_basics/annotation.html)
92. Annotated-VocalSet: A Singing Voice Dataset - MDPI, accessed June 1, 2025, [https://www.mdpi.com/2076-3417/12/18/9257](https://www.mdpi.com/2076-3417/12/18/9257)
93. MusicFace: Music-driven Expressive Singing Face Synthesis - The University of Texas at Dallas, accessed June 1, 2025, [https://www.utdallas.edu/~xguo/CVMJ2023.pdf](https://www.utdallas.edu/~xguo/CVMJ2023.pdf)
94. Datasets | Interactive Audio Lab, accessed June 1, 2025, [https://interactiveaudiolab.github.io/resources/datasets.html](https://interactiveaudiolab.github.io/resources/datasets.html)
95. Towards A (Better) Definition Of The Description Of Annotated M.I.R. Corpora | Request PDF, accessed June 1, 2025, [https://www.researchgate.net/publication/267383198_Towards_A_Better_Definition_Of_The_Description_Of_Annotated_MIR_Corpora](https://www.researchgate.net/publication/267383198_Towards_A_Better_Definition_Of_The_Description_Of_Annotated_MIR_Corpora)
96. An Annotated Corpus of Tonal Piano Music from the Long 19th Century | Empirical Musicology Review, accessed June 1, 2025, [https://emusicology.org/index.php/EMR/article/view/8903/8054](https://emusicology.org/index.php/EMR/article/view/8903/8054)
97. Paper page - Forest-of-Thought: Scaling Test-Time Compute for Enhancing LLM Reasoning, accessed June 1, 2025, [https://huggingface.co/papers/2412.09078](https://huggingface.co/papers/2412.09078)
98. Scaling LLM Test-Time Compute Optimally can be More Effective than Scaling Model Parameters - arXiv, accessed June 1, 2025, [https://arxiv.org/abs/2408.03314](https://arxiv.org/abs/2408.03314)
99. Diffusion Model Tutorial @ ICASSP25 - Google Sites, accessed June 1, 2025, [https://sites.google.com/view/diffusionmodeltutorialicassp25/home](https://sites.google.com/view/diffusionmodeltutorialicassp25/home)
100. [Blog] Diffusion based Text-to-Music Generation with Global and ..., accessed June 1, 2025, [https://research.samsung.com/blog/Diffusion-based-Text-to-Music-Generation-with-Global-and-Local-Text-based-Conditioning](https://research.samsung.com/blog/Diffusion-based-Text-to-Music-Generation-with-Global-and-Local-Text-based-Conditioning)
101. Diffusion based Text-to-Music Generation with Global and Local Text based Conditioning © 2025 IEEE. Personal use of this material is permitted. Permission from IEEE must be obtained for all other uses, in any current or future media, including reprinting/republishing this material for advertising or promotional purposes, creating new collective works, for - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2501.14680v1](https://arxiv.org/html/2501.14680v1)
102. Optimizing Transformer-Based Diffusion Models for Video ..., accessed June 1, 2025, [https://developer.nvidia.com/blog/optimizing-transformer-based-diffusion-models-for-video-generation-with-nvidia-tensorrt/](https://developer.nvidia.com/blog/optimizing-transformer-based-diffusion-models-for-video-generation-with-nvidia-tensorrt/)
103. aclanthology.org, accessed June 1, 2025, [https://aclanthology.org/2025.naacl-demo.19.pdf](https://aclanthology.org/2025.naacl-demo.19.pdf)
104. arXiv:2412.17667v2 [cs.SD] 27 Mar 2025, accessed June 1, 2025, [https://arxiv.org/pdf/2412.17667](https://arxiv.org/pdf/2412.17667)
105. Evaluating Interactive Music Systems : An HCI Approach, accessed June 1, 2025, [https://www.nime.org/proc/hsu2009/index.html](https://www.nime.org/proc/hsu2009/index.html)
106. archive.notam02.no, accessed June 1, 2025, [https://archive.notam02.no/arkiv/proceedings/NIME2009/nime2009/pdf/author/nm090128.pdf](https://archive.notam02.no/arkiv/proceedings/NIME2009/nime2009/pdf/author/nm090128.pdf)
107. Composing computer generated music, an observational study using IGME, accessed June 1, 2025, [https://www.nime.org/proceedings/2020/nime2020_paper12.pdf](https://www.nime.org/proceedings/2020/nime2020_paper12.pdf)
108. Composing computer generated music, an observational study using IGME: the Interactive Generative Music Environment - New Interfaces for Musical Expression, accessed June 1, 2025, [https://nime.org/proc/nime20_12/](https://nime.org/proc/nime20_12/)
109. M4singer svs naive rnn dp · Models - Dataloop, accessed June 1, 2025, [https://dataloop.ai/library/model/espnet_m4singer_svs_naive_rnn_dp/](https://dataloop.ai/library/model/espnet_m4singer_svs_naive_rnn_dp/)
110. arxiv.org, accessed June 1, 2025, [https://arxiv.org/pdf/2405.09940](https://arxiv.org/pdf/2405.09940)
111. www.isca-archive.org, accessed June 1, 2025, [https://www.isca-archive.org/interspeech_2022/guo22e_interspeech.pdf](https://www.isca-archive.org/interspeech_2022/guo22e_interspeech.pdf)
112. What is Data Augmentation and Why It Matters, accessed June 1, 2025, [https://www.fanruan.com/en/glossary/what-is-total-sales-and-why-is-it-important/data-augmentation](https://www.fanruan.com/en/glossary/what-is-total-sales-and-why-is-it-important/data-augmentation)
113. What Is Few-Shot Learning? | IBM, accessed June 1, 2025, [https://www.ibm.com/think/topics/few-shot-learning](https://www.ibm.com/think/topics/few-shot-learning)
114. Few-Shot Learning: Methods & Applications in 2025 - Research AIMultiple, accessed June 1, 2025, [https://research.aimultiple.com/few-shot-learning/](https://research.aimultiple.com/few-shot-learning/)
115. arxiv.org, accessed June 1, 2025, [https://arxiv.org/pdf/2308.13736](https://arxiv.org/pdf/2308.13736)
116. A Large Margin Algorithm for Speech-to-Phoneme and Music-to-Score Alignment - CS - Huji, accessed June 1, 2025, [https://www.cs.huji.ac.il/~shais/papers/KeshetShSiCh07.pdf](https://www.cs.huji.ac.il/~shais/papers/KeshetShSiCh07.pdf)
117. archives.ismir.net, accessed June 1, 2025, [https://archives.ismir.net/ismir2021/paper/000103.pdf](https://archives.ismir.net/ismir2021/paper/000103.pdf)
118. Daily Papers - Hugging Face, accessed June 1, 2025, [https://huggingface.co/papers?q=song%20generation](https://huggingface.co/papers?q=song+generation)
119. www.merl.com, accessed June 1, 2025, [https://www.merl.com/publications/docs/TR2025-012.pdf](https://www.merl.com/publications/docs/TR2025-012.pdf)
120. SMITIN: Self-Monitored Inference-Time INtervention for Generative Music Transformers, accessed June 1, 2025, [https://www.researchgate.net/publication/388481264_SMITIN_Self-Monitored_Inference-Time_INtervention_for_Generative_Music_Transformers](https://www.researchgate.net/publication/388481264_SMITIN_Self-Monitored_Inference-Time_INtervention_for_Generative_Music_Transformers)
121. A Survey on Music Generation from Single-Modal, Cross-Modal and Multi-Modal Perspectives - arXiv, accessed June 1, 2025, [https://arxiv.org/pdf/2504.00837](https://arxiv.org/pdf/2504.00837)
122. Music Foundation Model as Generic Booster for Music Downstream Tasks - arXiv, accessed June 1, 2025, [https://arxiv.org/html/2411.01135v3](https://arxiv.org/html/2411.01135v3)
123. A Survey on Music Generation from Single-Modal, Cross-Modal, and Multi-Modal Perspectives: Data, Methods, and Challenges - ResearchGate, accessed June 1, 2025, [https://www.researchgate.net/publication/390405892_A_Survey_on_Music_Generation_from_Single-Modal_Cross-Modal_and_Multi-Modal_Perspectives_Data_Methods_and_Challenges](https://www.researchgate.net/publication/390405892_A_Survey_on_Music_Generation_from_Single-Modal_Cross-Modal_and_Multi-Modal_Perspectives_Data_Methods_and_Challenges)
124. VMAs: Video-to-Music Generation via Semantic Alignment in Web Music Videos - CVF Open Access, accessed June 1, 2025, [https://openaccess.thecvf.com/content/WACV2025/papers/Lin_VMAs_Video-to-Music_Generation_via_Semantic_Alignment_in_Web_Music_Videos_WACV_2025_paper.pdf](https://openaccess.thecvf.com/content/WACV2025/papers/Lin_VMAs_Video-to-Music_Generation_via_Semantic_Alignment_in_Web_Music_Videos_WACV_2025_paper.pdf)
125. Analysis of Evaluation in Artificial Intelligence Music - Clausius Scientific Press, accessed June 1, 2025, [http://166.62.7.99/assets/default/article/2023/12/09/article_1702116237.pdf](http://166.62.7.99/assets/default/article/2023/12/09/article_1702116237.pdf)
126. Revival: Collaborative Artistic Creation through Human-AI Interactions in Musical Creativity, accessed June 1, 2025, [https://arxiv.org/html/2503.15498v1](https://arxiv.org/html/2503.15498v1)
127. Human-Centered AI Communication in Co-Creativity: An Initial Framework and Insights, accessed June 1, 2025, [https://arxiv.org/html/2505.18385v1](https://arxiv.org/html/2505.18385v1)
128. people.eecs.berkeley.edu, accessed June 1, 2025, [https://people.eecs.berkeley.edu/~bjoern/papers/shankar-validators-uist2024.pdf](https://people.eecs.berkeley.edu/~bjoern/papers/shankar-validators-uist2024.pdf)
