# Automatic Brain Tumor Segmentation
## 2022.04 ~ 2022.06

## 주제
- post-contrast T1-weighted MR image로부터 자동으로 tumor segmentation할 수 있는 알고리즘 개발

## 요약
- t1ce.nii.gz를 입력데이터로 받아서 segmentation의 결과를 같은 format의 nifti파일 (.nii.gz)로 저장하도록 했습니다.
- Segmentation의 결과는 label data에서의 1 (necrotic tumor core)과 4 (gd-enhancing tumor)영역을 포함하고 있도록 했으며, 두 영역에 해당하는 voxel은 1을 가지고, 나머지 voxel들은 모두 0을 가지도록 했습니다.
- 헬스케어용 오픈소스 프레임워크인 monai를 이용하여 3D U-Net을 통해 학습했습니다.

## 결과
### ver.1
#### validation set
- best mean dice : 0.9155
- epoch 100 average loss : 0.0922

![image](https://user-images.githubusercontent.com/84446424/182024685-e218bf7c-68a1-4235-8e23-7b33549dce76.png)

### test set
- dice similarity coefficient 평균 : 0.49

### ver.2
#### validation set
- best mean dice : 0.8233
- epoch 200 average loss : 0.0728

![image](https://user-images.githubusercontent.com/84446424/186707460-79d7ba95-b0fb-45db-bcda-31fb1de06fb3.png)

### test set
- dice similarity coefficient 평균 : 0.51

### ver.3
#### validation set
- best mean dice : 0.8785
- epoch 150 average loss : 0.0729

![image](https://user-images.githubusercontent.com/84446424/186707891-93a4a668-ba67-4cea-9110-389ca3afbbf1.png)

### test set
- dice similarity coefficient 평균 : 0.67
