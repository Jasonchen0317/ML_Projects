# Take at home problem: Variational Autoencoders 
The Main part of the code(including models, optimizing, training, testing, plotting, code explanation) are in take_at_home.ipynb. 

Other files: 1. data.py are for downloading and processing dataset. 2. flow.py contains Inverse Autoregressive Flows, Masked Autoencoder, etc.  3. masks.py includes utility functions for masked autoencoder.

Results: VAE generated images for all digits 0-9 are in 'numbers' directory, final latent variable plot and loss plot are in 'plot' directory.

## Results

### Loss plot(ELBO & log p(x))
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/plot/Loss_plot.png)

### VAE generated images for all digits 0-9
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/0.gif)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/1.gif)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/2.gif)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/3.gif)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/4.gif)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/5.gif)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/6.gif)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/7.gif)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/8.gif)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/numbers/9.gif)

### final latent variable(first & second dimension)
![](https://github.com/Jasonchen0317/CSGY-6613-Assignment/blob/main/TakeAtHome_Final/plot/scatter_plot.png)

