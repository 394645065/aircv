# aircv
Python Lib based on python-opencv2 *for python2.7+*

## Initialization

    import aircv as ac
    imsrc = ac.imread('youimage.png') # croped image
    imsch = ac.imread('searched.png') # searched.png contains youimage.png 

#### search image through SIFT

    print ac.find_sift(imsrc, imsch)

    Return value:
        if failure , return  []
        
        if find out the croped imapge ,return the croped image's location just like flowing:
        ((215, 45), [(160, 24), (161, 66), (270, 66), (269, 24)])  --- four location of rectangle image

#### if searched image contains mutiple croped image

    print ac.find_all_sift(imsrc, imsch, maxcnt = 0)

    maxcnt是可选参数，限制最多匹配的数量。输出eg， 一个都找不到返回None
    maxcnt is optional parameter that restrict max matched number, return 'None' 

    [((215, 45), [(160, 24), (161, 66), (270, 66), (269, 24)])]

#### 直接匹配查找图像

    print ac.find_template(imsrc, imsch)

期望输出 (目标图片的中心点，相似度)

    (294, 13), 0.9715

查找多个相同的图片，如在图形

![template1](testdata/2s.png)

中查找

![template2](testdata/2t.png)

    print ac.find_all_template(imsrc, imsch)

期望输出 (目标图片的中心点，相似度)

    [((294, 13), 0.9715), ...]

效果

![2res](testdata/2res.png)


## DEVELOPING

LICENCE under [MIT](LICENSE)
