# Retail-heatmap
**모델 구상** : YOLOv5 을 활용하여 동선 히트맵 그리기  
**활용 방안** : 기존 CCTV 혹은 추가로 설치된 카메라를 활용 소비자들의 
동선을 Heat map으로 그려 소비자 트래픽이 높은 지역과 그렇지 못한 콜드스폿 을 파악하여 판매율 을 높이기 위한 플래노그램을 설정할수 있다.
#
[프로젝트 PPT](https://docs.google.com/presentation/d/1d64s3t7sHgqcHHlNzcVv0wqbnUh-vqrH/edit?usp=sharing&ouid=116268806099058489984&rtpof=true&sd=true)
##  Head & Person Detection Model 

### Download model trained on crowd human using yolov5(m) architeture
Download Link:  [YOLOv5m-crowd-human](https://drive.google.com/file/d/1gglIwqxaH2iTvy6lZlXuAcMpd_U0GCUb/view?usp=sharing) 


<br/>

**Output (Crowd Human Model)**

![image](https://drive.google.com/uc?export=view&id=1ZOhDBRXj-Ra0vPL7iG6lrxCWAFhJTAti)

<br/>



## Test

```bash
$ python detect.py --weights crowdhuman_yolov5m.pt --source _test/ --view-img

```
  
  
## Test (Only Person Class)

```bash
python3 detect.py --weights crowdhuman_yolov5m.pt --source _test/ --view-img  --person
```

  
## Test (Only Heads)

```bash
python3 detect.py --weights crowdhuman_yolov5m.pt --source _test/ --view-img  --heads
```

## heatmap 작성
![image](https://github.com/ms827/Retail-heatmap/blob/6262fa70721fc3aa69d27667ee13ca642f034eb5/data/images/HD_CCTV_retail_store.PNG)

**YOLOv5를 활용 프레임별로 머리를 기준으로 x,y좌표를 뽑아낸 후 히트맵을 찍어준다**

![image](https://github.com/ms827/Retail-heatmap/blob/6262fa70721fc3aa69d27667ee13ca642f034eb5/data/images/heatmap%20(4).png)

## 평면 투영

![image](https://github.com/ms827/Retail-heatmap/blob/4cdb432fa90ec37ec2ea21e7dc0cdbf0980fbadf/data/images/heatmap%20(5).PNG)

**히트맵 정보의 직관성을 높이기 위하여 원근보정 후 평면투영을 시도해 보았다**



   
   
