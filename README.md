# YSActionsheet
# 效果图
![实际效果图](http://upload-images.jianshu.io/upload_images/6067780-215955ce2df466af.gif)

# 使用方法：
- ### block
```objective-C
YSActionSheet *actionSheet = [[YSActionSheet alloc] initWithButtonTitles:@[@"拍照", @"从相册选取"] cancelButtonTitle:@"取消"];
actionSheet.selectBlock = ^(NSInteger selectIndex, NSString *selectStr) {
    if (selectIndex == 0) {
    //拍照
    _desLB.text = @"你点击了拍照";
    }
    if (selectIndex == 1) {
    //从相册选取
    _desLB.text = @"你点击了从相册选取";
    }
};
    [actionSheet show];
```

- ### delegate
1. 遵循协议`<YSActionSheetDelegate>`
2. 弹出 **YSActionSheet** 
```objective-C
YSActionSheet *actionSheet = [[YSActionSheet alloc] initWithButtonTitles:@[@"拍照", @"从相册选取"] cancelButtonTitle:@"取消"];
actionSheet.delegate = self;
[actionSheet show];
```
3. 实现协议
```objective-C
- (void)ysActionSheet:(YSActionSheet *)actionSheet clickedButtonAtIndex:(NSInteger)index {
    if (index == 0) {
        //拍照
        _desLB.text = @"你点击了拍照";
    }
    if (index == 1) {
        //从相册选取
        _desLB.text = @"你点击了从相册选取";
    }
}
```

