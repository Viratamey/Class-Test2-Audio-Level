# Screenshots

![screenshot_20171010-155019](https://user-images.githubusercontent.com/30778983/31386915-24fd7a86-ade6-11e7-862b-14ea3bc26f66.jpg)
![screenshot_20171010-155027](https://user-images.githubusercontent.com/30778983/31386919-286fc1c4-ade6-11e7-8c44-6fcae5e8962e.jpg)
![screenshot_20171010-155037](https://user-images.githubusercontent.com/30778983/31386924-2afeb51c-ade6-11e7-83a2-e998511ebdbc.jpg)
![screenshot_20171010-155043](https://user-images.githubusercontent.com/30778983/31386928-2c9fd7c0-ade6-11e7-9c7f-632f9af72ec4.jpg)
![screenshot_20171010-155049](https://user-images.githubusercontent.com/30778983/31386930-2e3ea67e-ade6-11e7-9a79-25907e06e183.jpg)


#Algorithm
 public double soundDb(double ampl){
        return 20*Math.log10(getAmplitudeEMA()/ampl);
    }

    public double getAmplitude(){
        if(mediaRecorder != null){
            return (mediaRecorder.getMaxAmplitude());
        }else
            return (int) mEMA;
    }

    public double getAmplitudeEMA(){
        double amp = getAmplitude();
        mEMA = EMA_FILTER*amp + (1.0 - EMA_FILTER)*mEMA; //filtering y(n) = a*x + b*y(n-1)
        return (int) mEMA;
    }
    
    for this project we have taken ampl = 1, mEMA = 0.0, EMA_FILTER = 0.6;
    for default getAmplitudeEMA() = 0 so its log gives -infinity which we can see in one of the screenshot
    our threshold Audio level is 69dB in screenshots but uploaded code has threshold 80dB,which we can change by just changing the value of variable "threshold" in code
    
    
