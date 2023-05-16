# Oy ve Otesi Data for the 2023 Turkish General Election

This repository contains the unofficial numbers and reports reported by Oy ve Otesi volunteers for the 2023 Turkish General Election. The data is collected from Oy ve Otesi's API (api-sonuc.oyveotesi.org/api/v1/). The official results will be announced by the Supreme Election Council (YSK) after the finalization of the election results.

## Structure

The data is organized in the following structure:

```
.
└── 1
    └── school_xxxx.json
    └── school_xxxx.json
    └── ...
└── 2
    └── school_xxxx.json
    └── school_xxxx.json
    └── ...
└── ...
```

The directory names are the plate numbers of their respective cities. The ``xxxx`` in the file names represents the school's ID. The file contents are the JSON responses from the API. Each file contains ballot boxes from a single school; each ballot box contains: the ballot box number, number of total votes, a link that points to the photo of the respective wet-signed report and some other information and statistics.

## Contributing

PLEASE CONTRIBUTE! It takes time to fetch and download all the data for each city. If you have the time, please help us by fetching the data for a city and opening a pull request. Here are the steps:

1. Fork this repository
2. Clone https://github.com/kiliczsh/sandik :
   ```
   git clone https://github.com/egeakman/sandik
   ```
3. Change directory to ``sandik`` -> ``cd sandik``
4. Install dependencies : 
   ```
   pip3 install -r requirements.txt
   ```
5. Clone this repository as ``data`` while in the ``sandik`` directory : 
   ```
   git clone https://github.com/egeakman/2023-oveo-data data
   ```
6. Run the first script -> ``python3 main.py`` (It will ask you for the city's plate number, and after you enter it, it will start fetching the data. It will take some time depending on the number of schools in the city.)
7. Run the second script -> ``python3 bulk_tutanak.py`` (It will ask you for the path of the JSON file of the city you just fetched. It will then download all the data for the city. It will probably take some time depending on the number of ballot boxes in the city.)
8. Change directory to ``data`` -> ``cd data``
9.  Add the files -> ``git add .``
10. Commit the changes -> ``git commit -m "Add data for city xxxx"``
11. Push the changes -> ``git push origin main``
12. Open a pull request!
