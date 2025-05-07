# How to Build a Simple Web Scraper in Python Using BeautifulSoup

## Introduction
Web scraping is a powerful technique used to extract data from websites. Whether you're collecting product prices, headlines, or other useful data, Python makes the process simple and effective. In this tutorial, we’ll walk through building a basic scraper using `requests` and `BeautifulSoup`.

## Prerequisites
Before we start, make sure you have Python installed, and install the required libraries:

```bash

import requests  # Mengambil halaman dari internet
from bs4 import BeautifulSoup  # Membaca isi HTML-nya

url = "http://quotes.toscrape.com"  # Ini alamat websitenya
response = requests.get(url)  # Kita minta isi dari halaman ini
if response.status_code == 200:  # 200 artinya berhasil
    print("Page fetched successfully!")  # Kita berhasil ambil halamannya
    html = response.text  # Kita simpan isi HTML-nya ke variabel
else:
    print("Failed to retrieve the page")  # Kalau gagal

soup = BeautifulSoup(html, 'html.parser')  # Kita baca isi HTML dengan BeautifulSoup

quotes = soup.find_all('div', class_='quote')  
# Kita cari semua bagian <div class='quote'> ← isinya kutipan
for quote in quotes:  # Untuk setiap kutipan yang ditemukan
    text = quote.find('span', class_='text').get_text()  # Ambil teks kutipannya
    author = quote.find('small', class_='author').get_text()  # Ambil nama penulisnya
    print(f"{text} - {author}")  # Tampilkan hasil
def get_quotes():
    url = "http://quotes.toscrape.com"
    response = requests.get(url)
    soup = BeautifulSoup(response.text, 'html.parser')
    quotes = soup.find_all('div', class_='quote')

    results = []
    for quote in quotes:
        text = quote.find('span', class_='text').get_text()
        author = quote.find('small', class_='author').get_text()
        results.append({"text": text, "author": author})
    return results
for item in get_quotes():
    print(f"{item['text']} - {item['author']}")
