# yolov8pose_dfl_rknn_Cplusplus_dfl
yolov8pose 部署版本，将DFL放在后处理中，部署rk3588.

## 编译和运行

1）编译

```
cd examples/rknn_yolov8pose_dfl_demo

bash build-linux_RK3588.sh

```

2）运行

```
cd install/rknn_yolov8pose_demo_Linux

./rknn_yolov8pose_demo 

```

注意：修改模型、测试图像、保存图像的路径，修改文件为src下的main.cc

```

int main(int argc, char **argv)
{
    char model_path[256] = "/home/firefly/zhangqian/rknn/examples/rknn_yolov8pose_dfl_demo/model/RK3588/yolov8n_pose.rknn";
    char image_path[256] = "/home/firefly/zhangqian/rknn/examples/rknn_yolov8pose_dfl_demo/test.jpg";
    char save_image_path[256] = "/home/firefly/zhangqian/rknn/examples/rknn_yolov8pose_dfl_demo/test_result.jpg";

    detect(model_path, image_path, save_image_path);
    return 0;
}
```


# 测试效果

## onnx 测试效果

![test_onnx_result](https://github.com/user-attachments/assets/00d58a00-1bf1-4ab1-9568-4ad65b362f8b)


## rk3588上测试效果

![images](https://github.com/cqu20160901/yolov8pose_dfl_rknn_Cplusplus/blob/main/examples/rknn_yolov8pose_dfl_demo/test_result.jpg)

把板端模型推理和后处理时耗也附上，供参考，使用的芯片rk3588，模型输入640x640。

![image](https://github.com/user-attachments/assets/f60d76c5-c06d-42c6-9fe7-34f6eb1907b2)


# 导出onnx 参考

[【yolov8pose 部署rknn（rk3588）、部署地平线Horizon、部署TensorRT，部署工程难度小、模型推理速度快，DFL放后处理中】](https://blog.csdn.net/zhangqian_1/article/details/140767235)


