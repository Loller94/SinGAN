# SoundGAN

[Project](https://github.com/Loller94/SoundGAN) 
### Research Project implementation by Jane W. Osbøl & Cecilie C. K. Neckelmann, Software Design 

![](imgs/Applause.png)


### Citation
This implementation is an extension of the SinGAN-algorithm. Cited below are authors and official information about the source code:

```
@inproceedings{rottshaham2019singan,
  title={SinGAN: Learning a Generative Model from a Single Natural Image},
  author={Rott Shaham, Tamar and Dekel, Tali and Michaeli, Tomer},
  booktitle={Computer Vision (ICCV), IEEE International Conference on},
  year={2019}
}
```

## Code

### Install dependencies

```
python -m pip install -r requirements.txt
```


###  Train
To train the SoundGAN model run the following depending on sound or image input:

```
###  For running with sound, ‘ifSound’ must be set to True
python main_train.py --ifSound True --input_name <input_file_name>

### For running with images, ‘ifSound’ must be set to False
python main_train.py --ifSound False --input_name <input_file_name>
``` 

This will also use the resulting trained model to generate random samples starting from the coarsest scale (n=0).

To run this code on a cpu machine, specify `--not_cuda` when calling `main_train.py`

###  Random samples
To generate random samples from any starting generation scale, please first train the SoundGAN model on the desired image or sound (as described above), then run 

```
python random_samples.py --input_name <training_image_file_name> --mode random_samples --gen_start_scale <generation start scale number>
```

pay attention: for using the full model, specify the generation start scale to be 0, to start the generation from the second scale, specify it to be 1, and so on. 

###  Random samples of arbitrary sizes
To generate random samples of arbitrary sizes, please first train the SoundGAN model on the desired image or sound (as described above), then run 

```
python random_samples.py --input_name <training_image_file_name> --mode random_samples_arbitrary_sizes --scale_h <horizontal scaling factor> --scale_v <vertical scaling factor>
```



