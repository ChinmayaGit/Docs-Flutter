```
class _DriverDetailsState extends State<DriverDetails> with WidgetsBindingObserver{

  @override
  void initState() {
    super.initState();
    WidgetsBinding.instance.addObserver(this);
  }
  
  @override
  didChangeAppLifecycleState(AppLifecycleState state) {
    if (AppLifecycleState.paused == state) {}
    print("Status :" + state.toString());
  }
```
