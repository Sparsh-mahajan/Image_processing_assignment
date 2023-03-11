# Image_processing_assignment
repository to host the colab notebook containing solutions to the IVP assignment.

## Steps to use the colab notebook

### 1. Getting an image 
```python
from PIL import Image
import requests
from io import BytesIO

#enter URL of the image. open the image in new tab first and then copy and paste the URL here.
url = "https://marketplace.canva.com/EAFHm4JWsu8/1/0/1600w/canva-pink-landscape-desktop-wallpaper-HGxdJA_xIx0.jpg"

def getImageFromURL(url):
response = requests.get(url)
im = Image.open(BytesIO(response.content))
im.save('image.jpg')
```

1. open any image on chrome in a new tab. it should be in the format - https://xyz.com/abcdefgh.jpg
2. copy the link and paste it in the url variable. the link should be enclosed in strings.

### 2. Running the notebook.
1. go to runtime tab
2. select run all

### 3. Saving the notebook with outputs as a PDF.
#### Method 1 : using Jupyter nb convert
1. mount your drive to this colab notebook
2. go to files and save a copy of this notebook.
3. go to /content/drive/MyDrive/Colab Notebooks
4. copy path of the copy of the jupyter notebook file and put it in place of file path

```python
%cd /content

#run these.

!sudo apt-get install texlive-xetex texlive-fonts-recommended texlive-generic-recommended

!jupyter nbconvert --to pdf 'file_path'
```

#### Method 2 : using colabs print utility.
1. go to file->print and save file as pdf

#### Method 3 : downloading the notebook and using VS code.
1.  Download file as jupyter notebook under files.
2. open in VS Code after installing the jupyter extension for vs code
3. go to the 3 dots on the top shelf and choose export and then export as HTML
4. open the HTML file and save it as PDF
