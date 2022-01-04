# Singleton-

public class Singleton  {
    private static Singleton INSTANCE = null;
    private Singleton() {};
 
    public static Singleton getInstance() {
        if (INSTANCE == null) {
            INSTANCE = new Singleton();
        }
        return(INSTANCE);
    }
     
    // other instance methods can follow 
    
    public interface SingletonListener {
        void onSuccess(String success);
        void onError(String error);
    }
    
    public void func(boolean mCheck, SingletonListener listener){
          
        if(mCheck)
            listener.onSuccess("success");
        else
            listener.onError("error");
    }
}

在需要使用該功能的class的使用方法如下:

Singleton mSingleton;
mSingleton = Singleton.getInstance();
mSingleton.func("放入判斷值", new Singleton.SingletonListener() {
    @Override
    public void onSuccess(String success) {
    }
    @Override
    public void onError(String error) {
    }
});
