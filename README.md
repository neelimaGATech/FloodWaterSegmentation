# FloodWaterSegmentation
This project utilizes the Sen1Floods11 dataset to develop and evaluate deep learning models for flood detection using Sentinel-1 SAR and Sentinel-2 multispectral imagery. The dataset provides 4,831 georeferenced image chips labeled with water and flood masks across 11 flood events globally. It includes both hand-labeled and automatically derived annotations at 10 m resolution.

Citation: Bonafilia, D., Tellman, B., Anderson, T., & Issenberg, E. (2020). Sen1Floods11: A georeferenced dataset to train and test deep learning flood algorithms for Sentinel-1. CVPR Workshops. Link

Sen1Floods11 dataset consists of several types of files organized into folders for image chips, labels, metadata, and splits. Here's a breakdown:
1. Image Chips: File format:
   - Sentinel-1 SAR imagery:
     - GeoTIFF (.tif) with resolution 512 × 512 pixels at 10 m spatial resolution
     - VV and VH (log-scaled backscatter in dB)
     - Folder location: /features/s1/ 
     - File naming format: s1_{event_id}_{chip_id}_VV.tif, ..._VH.tif
   - Sentinel-2 Multispectral imagery
     - GeoTIFF (.tif)
     - 13 bands (B01–B12, including B8A)
     - Folder location: /features/s2/ 
     - File name format: s2_{event_id}_{chip_id}_{band}.tif
2. Labels (Flood / Water Masks)
   - Hand Labeled Masks
     - GeoTIFF (.tif)
     - Folder location: /labels/hand_labeled/
     - Label Values: 1 (water), 0 (no water), -1 (no data)
     - File format: hand_{event_id}_{chip_id}.tif
   - Automatically Labeled Masks (weak supervision)
     - GeoTIFF (.tif)
     - Folder location: /labels/weak_labels/
     - File name format: weak_{event_id}_{chip_id}.tif
4. Data Splits
   - CSV files listing the event and chip IDs used in training, validation, and testing
   - File names: flood_train_data.csv, flood_test_data.csv,flood_valid_data.csv
   - /splits/flood_handlabeled/
5. MetaData Files
   - Describes each image chip and flood event (location, date, satellite IDs, orbit info, chip count, split type, etc.)
   - Sen1Floods11_Metadata.geojson


 
