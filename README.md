# Veri Bilimi için 3 Kütüphane: Sweetviz, PyCaret, SHAP

Tek bir notebook'ta veri bilimi sürecinin üç adımı:

| Adım | Kütüphane | Ne yapar |
|---|---|---|
| 1. Veriyi tanı | [Sweetviz](https://github.com/fbdesignpro/sweetviz) | İki satır kodla bütün değişkenleri, target ile ilişkilerini ve train-test farkını tek HTML raporda gösterir |
| 2. Modeli kur | [PyCaret](https://github.com/pycaret/pycaret) | Ön işleme, model karşılaştırma, hiperparametre ayarı ve kaydetme işlerini birkaç satırla yapar |
| 3. Modeli açıkla | [SHAP](https://github.com/shap/shap) | Her değişkenin tahmini ne kadar artırıp azalttığını grafikle gösterir |

Veri seti: **Titanic** (yolcunun hayatta kalıp kalmadığını tahmin ediyoruz). Notebook veriyi internetten kendisi indiriyor.

👉 Notebook: [`veri_bilimi_3_kutuphane.ipynb`](veri_bilimi_3_kutuphane.ipynb)

## Kurulum

PyCaret 3.3 yalnızca **Python 3.9, 3.10 ve 3.11** sürümlerini destekliyor. Python 3.12 veya daha yeni bir sürümle kurulum hata verir.

[uv](https://docs.astral.sh/uv/) ile:

```bash
uv venv --python 3.11
uv pip install -r requirements.txt
```

pip ile (Python 3.11 kuruluysa):

```bash
python3.11 -m venv .venv
# Windows: .venv\Scripts\activate   |   macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
```

Sonra `jupyter notebook` ile notebook'u aç ve hücreleri sırayla çalıştır.

## Bilinen sorunlar

- **LightGBM 4.7**, PyCaret 3.3.2 ile çalışırken çöküyor. Bu yüzden `requirements.txt` dosyasında `lightgbm<4.7` kısıtı var.
- **Google Colab** Python 3.12 veya daha yeni bir sürüm kullandığı için PyCaret orada kurulmayabilir. Notebook'u yerel ortamda Python 3.11 ile çalıştırmanı öneririm.
