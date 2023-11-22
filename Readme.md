# Gold-Caps <img src="misc/goldcaps_logo.svg" width="30em">

This is a repository of synthetic caption datasets.

Currently we provide captions for the [Lakh MIDI Dataset-matched](https://colinraffel.com/projects/lmd/) music dataset (~30,000 tracks with accompanying MIDI files). 

### Check out some example captions on the [demo page](https://erl-j.github.io/Gold-Caps/).

The captions are intended to be used for research.

## How it's made?

We prompted the **gpt-4-1106-preview** chat endpoint to describe each track solely based on the track title and artist.

```
Give a general description of the track <title> by <artist_name> in one sentence.
Don't mention the title or artist.
```

## Use the datasets

The captioned datasets are provided as json files in the `datasets/` directory.

Current datasets:
- [gold-caps_lmd-matched_general-v0](https://github.com/erl-j/Gold-Caps/blob/main/datasets/gold-caps_lmd-matched_general-v0.json)


## How good are the captions?

TBD.

## Related Work

[1] [Noise2Music: Text-conditioned Music Generation with Diffusion Models](https://arxiv.org/abs/2302.03917)
*Qingqing Huang et al.*

In order to build their text conditioning the authors *“[…] take a pseudo-labeling approach via leveraging MuLan (Huang et al., 2022), a pre-trained text and music audio joint embedding model, together with LaMDA (Thoppilan et al., 2022), a pre-trained large language model, to assign pseudo labels with finegrained semantic to unlabeled music audio clips.”.* The process involves creating a large number of pseud’ocaptions using LaMDA and filtering them according to similarity to the audio computed through MuLAN. Unfortunately, the language model and the final music-audio embedding model are not publicly available

[2] [LP-MusicCaps: LLM-Based Pseudo Music Captioning](https://arxiv.org/abs/2307.16372)
*SeungHeon Doh et al.*

The authors use GPT-3.5-Turbo to turn a set of tags associated with the songs in three datasets (MusicCaps, Magna-tag-a-tune, Million Songs Dataset) into a textual descriptions. This is achieved using various prompting strategies and evaluated using both objective and subjective metrics.

[3] [LLark: A Multimodal Foundation Model for Music](https://arxiv.org/abs/2310.07160)
*Josh Gardner et al.*

The authors built a model capable of addressing many tasks in music understanding, including captioning. The model features a pretrained generative audio encoder, a pretrained language model, and a simple multimodal projection module that maps encoded audio into the LLM embedding space. Variants of ChatGPT were used to merge the heterogenous information in various datasets into a uniform input for instruction tuning.

## Todo

We plan on releasing captions for the following datasets:
- [GiantMIDI](https://example.com/giantmidi).
- [VoxCelebA](https://example.com/voxceleba).

We are also experimenting with other prompts focusing on various aspects of the tracks (e.g vibe, arrangement, production) and audiences (e.g. french-speakers, seniors, musicians, non-musicians) (see demo page).


