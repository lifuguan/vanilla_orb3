# ORB-SLAM3 M2DGR跑分

1. 打开roscore
```shell
roscore
```

2. 准备转换数据格式
```shell
rosrun image_transport republish compressed in:=/camera/left/image_raw/ raw out:=/camera/image_raw/
```

3. 打开ORB-SLAM3
```shell
rosrun ORB_SLAM3 Mono Vocabulary/ORBvoc.txt config/M2DGR/paperleft.yaml
```

4. 播放数据集
```shell
rosbag play slam_data/M2DGR/walk_01.bag
```

5. 验证结果
```shell
evo_ape tum slam_data/M2DGR/walk_01.txt output/1.txt -vaps --plot --save_plot ./output/KeyFrameTrajectory
```

