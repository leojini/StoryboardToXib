Storyboard to xib

1. Main.storyboard, LaunchScreen.storyboard 를 삭제한다.
2. Info.plist / Launch screen interface file base name : Value를 지운다.
3. Info.plist / Main storyboard file base name : 삭제
4. ViewController.xib 추가
	: File's Owner의 Custom Class에 ViewController로 설정한다.
	: File's Owner의 Outlets의 view를 실제 view와 연결한다.
5. AppDelegate.m의 didFinishLaunchingWithOptions 메소드에 아래 코드를 추가한다.
	self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];
    ViewController *controller = [[ViewController alloc] initWithNibName:@"ViewController" bundle:nil];
    self.window.rootViewController = controller;
    self.window.backgroundColor = [UIColor whiteColor];
    [self.window makeKeyAndVisible];