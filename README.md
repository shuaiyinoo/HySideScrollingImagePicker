# HySideScrollingImagePicker

![image](https://raw.githubusercontent.com/wwdc14/HySideScrollingImagePicker/FixBranch/HySideScrollingImagePicker/Untitled.gif)

1.已修复Block不存在导致crash
2.已修复CollectionView多选重用,导致得到的数据混乱bug

修复BUG:获取系统图片,图片过多的时候会崩溃.

//显示图片预览:

    HySideScrollingImagePicker *hy = [[HySideScrollingImagePicker alloc] initWithCancelStr:@"取消" otherButtonTitles:@[@"拍摄",@"从相册选择",@"更多"]];
    hy.isMultipleSelection = false;
    
    hy.SeletedImages = ^(NSArray *GetImages, NSInteger Buttonindex){
        
        NSLog(@"GetImages-%@,Buttonindex-%ld",GetImages,(long)Buttonindex);
        
    };
    [self.view insertSubview:hy atIndex:[[self.view subviews] count]];
    
//显示自定义ActionSheet

    HyActionSheet *action = [[HyActionSheet alloc] initWithCancelStr:@"取消" otherButtonTitles:@[@"退出登录"] AttachTitle:@"退出登录后不会删除任何历史数据, 下次登录依然可以使用本账号"];
    
    [action ChangeTitleColor:[UIColor redColor] AndIndex:1];
    
    [self.view addSubview:action];
    
    action.ButtonIndex = ^(NSInteger Buttonindex){
    
        NSLog(@"index--%ld",Buttonindex);
    
    };
