# fastai_audio

This work was based on the excellent work from [sevinfx/fastai_audio](https://github.com/sevenfx/fastai_audio).

However, most of codes has been reengineered, with the notable exception of spectograms generation using PyTorch.
The benefit from this code review is:
- Preprocessing
  - Management of mono and stereo files, including for dataloader and models.
- Performance improvements: 
  - Files can be read by Scipy (faster but doesn't work for some wave) or Librosa (slower but works on almost all files)
- Interpretation:
  - Ability to see batch using standard FastAI show_batch methods (useful to see data after data augmentation methods)
  - Interpretation with [Grad-CAM](http://openaccess.thecvf.com/content_ICCV_2017/papers/Selvaraju_Grad-CAM_Visual_Explanations_ICCV_2017_paper.pdf) by adapting the existing FASTAI plot_top_losses to audio data with the new method plot_audio_top_losses


Several notebooks have been created to compare this work with several dataset and benchmarks (see inside notebooks folder).
**This work is close to SOTA on audio classification in UrbanSound8k (performance from this work 96.8% without CV vs 97.5% with CV for SOTA)**

Note: This is an unofficial module add-on for [`fastai v1`](https://github.com/fastai/fastai) library.  

##### Related Links
* [fastai v1 docs](https://docs.fastai.com)
* [Audio Classification using FastAI and On-the-Fly Frequency Transforms](https://towardsdatascience.com/audio-classification-using-fastai-and-on-the-fly-frequency-transforms-4dbe1b540f89)

#### Dependencies
* python 3.7
* fastai 1.0.51
* librosa 0.6.2
* soundfile 0.10.2

#### Installation

To use the notebooks as is, a symbolic link needs to be created from ./notebooks/fastai_audio to ./fastai_audio
