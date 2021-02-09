# search-papers

# Running for the first time

This piece of software only runs for Windows Operating System.
Follow the following steps for running the scripts.
1. Make a new folder somewhere in your filesystem (say in Desktop) and name it as environments.
2. Open command prompt and go inside this folder i.e. <path to environments>\environments.
3. Once you are inside the enivornments folder, check whether python is installed using : python --version 
   If you don't have python installed, you will have to install it from https://www.python.org/downloads/ . Make sure you download version >= 3.7.
   Also, make sure to add path of python.exe to sytem environment variables. Once, you install a version >=3.7, go to environments folder and 
   check again : python --version
   
4. Inside evironments folder, make a new virtual environment using: python -m venv env
5. Activate the environment using: env\Scripts\activate
   Once, the environment is activated you will see something like: (env) <path to environments>\environments\ >
6. Now, clone this repostiory using: git clone https://github.com/fluxgatedesign/search-papers/
7. Go inside this repository using: cd search_papers
8. Go inside papers_search using: cd papers_search
9. Install the required dependecies using: pip install -r requirements.txt
   This will install selenium and pandas.

10. Check the version of your chrome using: go to chrome > click on three dots on top right corner > Help > about google chrome.
   If you are using chrome version : 88.something, proceed to step 11 otherwise download the chromedriver for your chrome version from
   https://chromedriver.chromium.org/downloads. Click on the link link for your version (say if you have chrome version 89, then click on 
   ChromeDriver 89.0.4389.23). Download chrome_driver.zip and extract the folder. This will give you an executable file named chromedriver.exe.
   Copy this file and paste it in the folder : <path to environments>\environments\search_papers\chrome_driver. You will have to replace chromedriver.exe
   file with the chrome driver file for your version.
11. Now go to folder <path to environments>\environments\papers_search. Make sure your environment is activated while you follow from step 6 onwards.
    Now type : python command_line_search.py -h
    You will find different options you can use to search arxiv, prl and google scholar.
12. To search a phrase (say fluxgate) in prl, type: python command_line_search.py --query "fluxgate" --max_page 2 -p
    This will automatically open chrome, search in prl and save the results in the data folder as a csv file. 
    --query flag is used to search the phrase i.e. if you wish to search gradiometer, you should type: python command_line_search.py --query "gradiometer" --max_page 2 -p
    --max_page searches the results in specified number of pages. Say, if you wish to search  gradiometer in first 5 pages in prl, you should type:
         python command_line_search.py --query "gradiometer" --max_page 5 -p
    -p search in prl, -ar will search in arxiv, --gs will search in google scholar, -a will search all of them.
       So, if you wish search  gradiometer in first 6 pages in google scholar, you should type:
       python command_line_search.py --query "gradiometer" --max_page 6 --gs
    Note: --max_page can be ignored. In that case, it will by default search first 10 pages and the command will look like:
            python command_line_search.py --query "gradiometer" --gs
13. Once the command runs successfully, files with .csv extension will be created in the folder : <path to environments>\enivronments\search-papers\data.
14. You can deactivate the evironment using: deactivate 
  
  
  
# Running for >= second time:
1. Open command prompt and go to environments folder using: cd <path to enivornments>\environments.
2. Activate python virtual environment using: env\Scripts\activate
3. Go to papers_search inside search-papers using: cd search-papers\papers_search
4. Run the python script and search the term you want. Make sure to keep that term inside double inverted commas. 
   Eg. python command_line_search.py --query "fluxgate" --max_page 6 -a 
   This will search for fluxgate in all the journals (arxiv, prl and google scholar) upto first 6 pages in each of them.
5. Once the code run properly, you can see your search results as a .csv file in data folder. You can view this using excel, google sheets or notepad.
6. Deactivate the environment using : deactivate
7. Exit the command prompt.

