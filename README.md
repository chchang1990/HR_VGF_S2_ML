# Generating high-resolution (10-m) vegetation greenness fraction with Sentinel-2, SMAP imagery, and machine learning

**Vegetation Greenness Fraction (VGF)** describes the proportion of green vegetation over an area. High resolution VGF data is widely used in many aspects. One of its applications is to **monitor the vegetation growth, and crop yields, which provide valuable insight for agriculture activity** (<a href="https://www.mdpi.com/2072-4292/11/19/2324">Tao et al., 2019</a>).

Conventionally, VGF are commonly calculated with the **"<i>relative vegetation abundance algorithm</i>" by leveraging vegetation index (VI) derived from remotely sensed data**. Simply put, this algorithm calculates VGF as the ratio between the instaneous and the maximal VIs relative to the bare-soil VI. However, **this algorithm requires accurate maximal and bare-soil VIs to give us a skillful VGF estimation, which is quite challenging since they can vary in different geographic regions, and vegetation types** (<a href="https://www.sciencedirect.com/science/article/pii/S0924271619302783">Gao et al., 2020</a>). The level 4 product of the Soil Moisture Active Passive (SMAP) satellite mission, SPL4SMGP, provides the VGF data. However, its 9-km spatial resolution is coarse and may not be fine enough for practical use.

In this Colab script, **I demonstrated a machine learning-based approach to generate high-resolution (10-m) VGF from the Sentinel-2 (S2) imagery by leveraging the Google Earth Engine**. Specifically, I used randomly sampled data from spatiotemporally coincident historical S2 Normalized Difference Vegetation Index (NDVI) and SMAP VGF from 2019 to 2021 as training data to train a random forest regression model. With this model, any updated high-resolution (10-m) S2 NDVI can be used as input to generate the corresponding high-resolution (10-m) VGF.

**Original 9-km resolution SMAP VGF**
![](https://drive.google.com/uc?export=view&id=1-oI1EAI2WHhfVgHnrWQXIwHanhpW2rqw)

**Sentinel-2 high-resolution (10-m) VGF estimated with machine learning over the same area at the same time as the above figure**
![](https://drive.google.com/uc?export=view&id=1-pel6cvEEFPw8z0vghtUHgSxVEdG2wQf)
