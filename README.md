README.txt

After downloading the files from github or using git clone please ensure your directory structure looks like this
Directory Structure:-
main_folder
	|
	| —------- app.py
	|
	| —------- best_model.pt
	|
	| —------- frontend.py
	|
	| —------- image_classification.ipynb
	|
	| —------- Image_Classification_Report.docx
	|
	| —------- inference.py
	|
	| —------- README.txt

##On windows please use command prompt
It is recommended to create a new virtual environment
```python -m venv image_classification``` (Windows)
```python3 -m venv image_classification``` ( MacOS, linux)

```image_classification\Scripts\activate``` (Windows)
```source image_classification/bin/activate``` (MacOS, linux)

Libraries required for image_classification: 
torch torchvision fastapi uvicorn matplotlib python-multipart streamlit
```pip install torch torchvision fastapi uvicorn matplotlib python-multipart streamlit```

#For Training (optional): 
The training code is provided in the image_classification.ipynb. On running this file the dataset will be installed in the main_folder, also the trained model will be saved in a new directory named models in the main_folder as well.
In order to use the trained_model.pt, please edit the model_path variable in inference.py mentioned here 
model_path = os.path.join( main_folder, 'best_model.pt' )

After training the directory structure should look like this

main_folder
	|
	| —------- image_classification.ipynb
	|
	| —------- frontend.py
	|
	| —------- app.py
	|
	| —------- best_model.pt
	|
	| —------- README.txt
	|
	| —------- cifar10
	|		|
	|		| —------ train
	|		| 
	|		| —------ test
	|
	| —------- models
	|		|
	|		| —------- trained_model.pt


#For inference:
Run the FastAPI from your terminal
```uvicorn app:app --reload```

Open another instance of command prompt, and enter the main_folder by changing directory appropriately.
Now activate the virtual environment using 
```image_classification\Scripts\activate``` (Windows)
```source image_classification/bin/activate``` (MacOS, linux)

Run the streamlit frontend on your localhost using the command
```streamlit run frontend.py```

The streamlit frontend will open in the browser, please upload either a ‘png’, ‘jpg’ or a ‘jpeg’ file by clicking on the Browse files button.
