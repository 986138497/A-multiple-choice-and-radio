# A-multiple-choice-and-radio
A multiple-choice and radio


//多选按钮和单选按钮

1.首先先导入头文件
2.定义全局变量 CheckGroup *checkGroup;
3.CheckBox *checkBox1=[[CheckBox alloc]initWithFrame:CGRectMake(0, 50, 200, 30)];
    //checkBox1.text=@"测试1";
    checkBox1.value=1;

    
    CheckBox *checkBox2=[[CheckBox alloc]initWithFrame:CGRectMake(0, 90, 200, 30)];
    //checkBox2.text=@"测试2";
    checkBox2.value=2;
    CheckBox *checkBox3=[[CheckBox alloc]initWithFrame:CGRectMake(0, 130, 200, 30)];
    checkBox3.text=@"测试3";
    checkBox3.value=3;
    NSArray *arr=[NSArray arrayWithObjects:checkBox1,checkBox2,checkBox3, nil];
    checkGroup=[[CheckGroup alloc]initWithFrame:CGRectMake(20, 100, 150, 200) WithCheckBtns:arr];
    checkGroup.isCheck=NO;
//    checkGroup.backgroundColor=[UIColor yellowColor];
    [self.view addSubview:checkGroup];
     UIButton *btn=[[UIButton alloc]initWithFrame:CGRectMake(20, 320, 100, 30)];
    btn.backgroundColor=[UIColor redColor];
    [btn setTitle:@"确定" forState:UIControlStateNormal];
    [btn addTarget:self action:@selector(btnAction) forControlEvents:UIControlEventTouchUpInside];
    [self.view addSubview:btn];
    
    
    4.-(void)btnAction
{
    if (checkGroup.isCheck) {
        for (int i=0; i<checkGroup.selectTextArr.count; i++) {
            NSLog(@"%@,%@",checkGroup.selectTextArr[i],checkGroup.selectValueArr[i]);
        }
    }else{
        NSLog(@"%ld----%@",(long)checkGroup.selectValue,checkGroup.selectText);
    }
    
}
