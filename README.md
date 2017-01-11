### Short description of the Jupyter notebook to/from Python converter files.

It can be difficult to version control Jupyter notebooks, especially if you don't want to track changes in the output, just the code.  While Jupyter can generate python files from a notebook, there is no cell type metadata and information about markdown cells is completely lost.

#### To automatically save your Jupyter notebook as a Python file with metadata, add the text in **jupyter_notebook_config.txt** to your jupyter_notebook_config.py file.

* On Windows, this file can generally be found in the C:\Users\YOUR_USER_NAME\\.jupyter directory.  If there is no config file in this directory, create one with ```jupyter notebook --generate-config``` at the command line.
	* (If you can't find your .jupyter folder, try ```ipython locate profile default```.  This should find your .ipython folder which is likely in the same directory as your .jupyter folder.)
* Once this is done, a .py file with the same name as your notebook will be saved in the same directory every time your notebook is saved.  
* You can verify this is working in the terminal window running your
notebook, which will print a note everytime the .py file is saved. 
* Files named "Untitled" will not be saved.


#### If you do not want to run this automatically, but would like to run on individual notebooks, use the following scripts:

* **notebook_v4_to_py.py** converts a Jupyter notebook to a .py file that preserves
cell metadata. The conversion can be done manually by running the following
command:

	```python notebook_v4_to_py.py -f notebook_filename.ipynb```
    

* **py_to_notebook_v4.py** converts a .py file back to a Jupyter notebook, using the following command:

	```python py_to_notebook_v4.py -f py_filename.py```
    

* Call the scripts with argument "--overwrite" to overwrite existing .ipynb or
.py files.

* Call the scripts with argument "--dry-run" to simulate (print out) what would
happen.