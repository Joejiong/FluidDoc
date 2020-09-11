.. _cn_api_vision_transforms_RandomResizedCrop:

RandomResizedCrop
-------------------------------

.. py:class:: paddle.vision.transforms.RandomResizedCrop(output_size, scale=(0.08, 1.0), ratio=(3. / 4, 4. / 3), interpolation=cv2.INTER_LINEAR)

将输入图像按照随机大小和长宽比进行裁剪。
会根据参数生成基于原图像的随机比例（默认值：0.08至1.0）和随机宽高比（默认值：3./4至4./3）。
经过此接口操作后，输入图像将调整为参数指定大小。

参数
:::::::::
        
    - output_size (int|list|tuple) - 输出图像大小，当为单个int值时，生成output_size大小的方形图片，为(height,width)格式的数组或元组时按照参数大小输出。
    - scale (list|tuple) - 基于原图选定的需要进行裁剪的范围，默认值：（0.08，1.0）。
    - ratio (list|tuple) - 裁剪后的目标图像宽高比范围，默认值： (0.75, 1.33)。

返回
:::::::::

    ``numpy ndarray``，随机裁剪和改变大小后的图像。

代码示例
:::::::::
    
.. code-block:: python

    import numpy as np
    from paddle.vision.transforms import RandomResizedCrop
    
    
    transform = RandomResizedCrop(3)
    fake_img = np.random.rand(5, 5, 3).astype('float32')

    print('original image:')
    print(fake_img)

    fake_img = transform(fake_img)

    print('output image:')
    print(fake_img)
    
    """
    original image:
    [[[0.22199318 0.8707323  0.20671916]
    [0.91861093 0.4884112  0.61174387]
    [0.7659079  0.518418   0.2968005 ]
    [0.18772122 0.08074127 0.7384403 ]
    [0.4413092  0.15830986 0.87993705]]

    [[0.27408648 0.41423503 0.29607993]
    [0.62878793 0.5798378  0.5999292 ]
    [0.26581913 0.28468588 0.2535882 ]
    [0.32756394 0.1441643  0.16561286]
    [0.96393055 0.9602267  0.18841465]]

    [[0.02430656 0.20455554 0.6998436 ]
    [0.7795146  0.02293309 0.5776629 ]
    [0.00164217 0.5154726  0.6397952 ]
    [0.98562443 0.2590976  0.8024969 ]
    [0.8704831  0.92274964 0.00221421]]

    [[0.46948838 0.98146874 0.3989448 ]
    [0.8137325  0.5464565  0.7708541 ]
    [0.48493108 0.02911156 0.08652569]
    [0.11145381 0.2512451  0.9649153 ]
    [0.6317661  0.8166602  0.566082  ]]

    [[0.6353562  0.8119024  0.9266826 ]
    [0.91262674 0.82481074 0.09420273]
    [0.36104843 0.03550903 0.54635835]
    [0.7961427  0.0511428  0.18866773]
    [0.36547777 0.24429087 0.79508746]]]
    output image:
    [[[0.7659079  0.518418   0.2968005 ]
    [0.18772122 0.08074127 0.7384403 ]
    [0.4413092  0.15830986 0.87993705]]

    [[0.26581913 0.28468588 0.2535882 ]
    [0.32756394 0.1441643  0.16561286]
    [0.96393055 0.9602267  0.18841465]]

    [[0.00164217 0.5154726  0.6397952 ]
    [0.98562443 0.2590976  0.8024969 ]
    [0.8704831  0.92274964 0.00221421]]]
    """