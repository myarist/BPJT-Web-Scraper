# BPJT-Web-Scraper
Here are some files from the BPJT site scrap project

Here, I use selenium web driver for doing the scrap

```
from selenium import webdriver
from selenium.webdriver.support.select import Select
```

I used BPJT website as the target

````
url = "http://bpjt.pu.go.id/cek-tarif-tol"
````

![Website BPJT](https://github.com/MyArist/BPJT-Web-Scraper/blob/master/README/cek%20tarif.png)

Then, I use Edge Driver for the Selenium, because this is my default browser

```
driver = webdriver.Edge("msedgedriver.exe")
driver.get(url)
```

Here is the list of variables I create:

```
time     = 0.25
data     = []
ruas     = Select(driver.find_element_by_xpath('//*[@id="toll_road"]'))
masuk    = Select(driver.find_element_by_xpath('//*[@id="toll_gates"]'))
keluar   = Select(driver.find_element_by_xpath('//*[@id="toll_gates2"]'))
golongan = Select(driver.find_element_by_xpath('//*[@id="veh_gr"]'))
tarif    = driver.find_element_by_xpath('//*[@id="tarif"]')
```

Variable | Function
---: | :---
time | add delay when iterating, give time for the website to load
data | save the final result later
ruas | save options of the "Ruas Jalan Tol" dropdown
masuk | save options of the "Gerbang Masuk" dropdown
keluar | save options of the "Gerbang Keluar" dropdown
golongan | save options of the "Golongan Kendaraan" dropdown
tarif | save the value of "Tarif Tol"
