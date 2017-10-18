# CustomFontDemo
iOS自定义字体设置与系统自带的字体
1.下载所需要的ttf文件,导入工程中,在Info.plist中添加一项:Fonts provided by application,填写字体文件名称加后缀.如图: Info.plist配置

2.前往TARGETS -> Build Phases -> Copy Bundle Resources中添加字体文件 Copy Bundle Resources配置
![a](http://s15.sinaimg.cn/mw690/005R98Amzy7f32EYiLk5e&690)

3.通过眼力找到字体文件对应的fontName (command + F 搜索你想要的文件名称)
NSArray *familyNames = [UIFont familyNames]; 
for( NSString *familyName in familyNames ) { 
 NSArray *fontNames = [UIFont fontNamesForFamilyName:familyName]; 
 for( NSString *fontName in fontNames ) { 
   printf( "\tFont: %s \n", [fontName UTF8String] );
 } 
}
![a](http://s1.sinaimg.cn/large/005R98Amzy7f32MNm1210&690)


4.使用自定义字体
self.Label.text = @"钟齐流江毛笔草体"; 
self.Label.font = [UIFont fontWithName:@"DigifaceWide" size:30]; self.Label2.text = @"蒙纳漫画体"; 
self.Label2.font = [UIFont fontWithName:@"MComicHK-Medium" size:30];


