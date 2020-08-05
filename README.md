换了个工作，又有服务器可以炼丹了！有时间我看看这玩意还能用吗
### I have fixed the bug and update the model, you can view the new code and commit
### 我已经修复了之前提到的BUG并且更新的模型，你可看diff来判断。(终于更了

# Convolutional Recurrent Neural Network

This software implements the Convolutional Recurrent Neural Network (CRNN) in caffe. Origin software could be found in [crnn](https://github.com/bgshih/crnn) .You can also find the [cnn.pytorch](https://github.com/meijieru/crnn.pytorch) 


# crnn.caffe

The initial environment for this project is [warpctc-caffe](https://github.com/xmfbit/warpctc-caffe).
The network framework is from  [cnn.pytorch](https://github.com/meijieru/crnn.pytorch) ,it also can be read from  [crnn](https://github.com/bgshih/crnn) 

CNN-LSTM-CTC, CNN can get BxC feature vectors,they are as the input of LSTM,LTSM can work the vertors in time_step.From CRNN you can get better way to work as the end-to-end character recognition.At first,I just use the LSTM-CTC( [warpctc-caffe](https://github.com/xmfbit/warpctc-caffe) ) to work with the license plate recognition.Loss is very slow convergence and it always overfitting.The result don't like the [cnn.pytorch](https://github.com/meijieru/crnn.pytorch) ,I run the crnn.pytorch to work with these license plate.Finally,I am determined to write the crnn.caffe.The caffe environment is easier to make a product.

# Build

clone the code

> git clone git@github.com:yalecyu/crnn.caffe.git
>
> cd crnn.caffe
>
> make
> 
> make pycaffe

If there some problems,you can confirm your basic the setting of caffe and server.Build this project is the same way like build caffe.

# Test
For example,I run a smaill captcha model.You can use like: ./build/examples/cpp_recognition/recognition.bin (your).jpg (your).prototxt (your).caffemodel

> ./build/examples/cpp_recognition/recognition.bin data/captcha/11111-50550.png examples/crnn/deploy.prototxt examples/crnn/model/crnn_captcha_iter_1000.caffemodel 

![avatar](https://github.com/yalecyu/crnn.caffe/blob/master/data/captcha/11111-50550.png)
"5---0-5--55-0"   ====>    "50550"

# Train
#### make data
> python examples/crnn/generate_captcha.py
>
> python examples/crnn/generate_dataset.py


* You can read the image at data/captcha/ 

#### train
> ./examples/crnn/train.sh

# Acknowledgements

The authors would like to thank the developers of  [crnn](https://github.com/bgshih/crnn)  [crnn.pytorch](https://github.com/meijieru/crnn.pytorch)  [warpctc-caffe](https://github.com/xmfbit/warpctc-caffe),without your help ,I can't write the crnn.caffe.When I send the email to you,always get the suggest quickly.

Please let me know if you encounter any issues.
