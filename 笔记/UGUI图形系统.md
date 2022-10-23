### 画布渲染
            屏幕空间：永远显示在屏幕最前端
            缩放模式里可以控制UI的缩放,开发的时候参考分辨率


### 图像、文本框、按钮、输入框的脚本交互

            InputField userInput;
         Button logonBtn;
            userInput = transform.Find("UserInputField").GetComponent<inputField>();   //查找到物体，获取到组件
            logonBtn= transform.Find("LogonBtn").GetComponent<Button>();   //查找到物体，获取到组件
            logonBtn.onClick.AddListener(LogonBtnOnClick);

         void LogonBtnOnClick(){ 
             string account = userInput.text;      //获取文本框的文本

         }



         public Sprite bg;
         修改图片的精灵
            transform.Find("BG").GetComponent<Image>().sprite = bg;



            跳转网页事件
            Application.OpenURL("变量URL");


### 切换（Toggle）
            Toggle toggle;
           toggle = transform.Find(""Toogle).GetComponent<Toggle>();
           if(toggle.isOn == true)           //判断用

            可以界面上设置开关组，只能选择一个


### 滚动条
          Slider slider;
          slider = transform.Find("Slider").GetComponent<Slider>();   //查找到物体
          slider.onValueChanged.AddListener(OnValueChanged);
       void OnValueChanged(float value){
             slider.value         //获取滚动条的值
        }

### 滚动视图
          里面可以放很多东西，下面和右边有滚动条可以滚动查看东西（图片等等），比如用来做协议文本框等，说不定可以做装备栏
         遮罩：可以遮罩一部分，让一部分显示 
        水平组件，垂直组件，网格布局组件添加layout可以让滚动视图里的元素水平或垂直排列
    
        内容尺寸自适应(下面代码是按A键动态克隆数据。)
        public GameObject hero;
      public Transform Content;

      update函数里
        if(Input.GetKeyDown(KeyCode.A))
         {      
            GameObject hero = GameObject.Instantiate(hero);
             hero.transform.parent=Content;
         }
      
         脚本挂载
        

### 矩形变换
        锚点：确定屏幕到四条边的距离（比例）是多少
        轴心点：会影响缩放


组件里可以加特效，比如图片加轮廓特效

#### 两张图片，一张水平填充，可以做滑动条，就像进度条一样。下面的代码是实现滑动的代码。经常用到场景切换里
     public Image image
    start函数里
      float value = 0.00001f;
    for(int i = 0 ;i <100000 ; i++){
         image.fillAount = value*i;
     }