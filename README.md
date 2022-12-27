# Simple MNIST classification using Keras

Kerasın kendi sitesindeki örnek proje referans alınmıştır.
- https://keras.io/examples/vision/mnist_convnet/

### Programın çıktısı
![image](https://user-images.githubusercontent.com/59448872/151628424-fb24f721-4b1d-460b-b1df-99cd14a3ad3b.png)
![image](https://user-images.githubusercontent.com/59448872/151628558-878e95a7-231a-44c1-a911-2ffdfcd0c8a3.png)

-----

## TensorBoard
Tensorboard, modelimiz ile ilgili parametreleri, zamana göre grafikleri hazır bir şeklide analiz etmemize olanak sağlar.

Tensorboardı açmak için;
1. Eklenmesi gereken kütüphaneler.
```python
from keras.callbacks import TensorBoard
import time
from datetime import datetime, timedelta
```
2. Callback için değişken oluşturuldu.
```python
log_dir = "/tmp/tensorboard/" + datetime.now().strftime("%Y%m%d-%H%M%S")
kerasboard = TensorBoard(log_dir=log_dir,
                        histogram_freq=1,
                        batch_size=batch_size,
                        write_grads=False)
```
3. Modelimizi fit ederken callback parametresine liste şekilde verilmesi gereklidir.
```python
model.fit(x_train, y_train ,callbacks=[kerasboard,earlyStoping], batch_size=128 ,epochs=20, validation_split=0.10)
```

4. Aşağıdaki kodun cıktısını, anaconda prompt terminaline yazdıktan sonra, çıktı olarak `TensorBoard 2.11.0 at http://localhost:6006/` buna benzer bir çıktı verecektir. Örnek resim aşağıdaki gibidir.
```python
print("tensorboard --logdir="+kerasboard.log_dir)
```

<p align="center">
  <img src="https://user-images.githubusercontent.com/59448872/209555869-fd13aa96-874e-4dc3-9de4-886acc65a507.png" />
</p>



`http://localhost:6006/` tarayıcınızdan actığınız zaman tensorboard ekranında ulaşabileceksiniz.

<p align="center">
  <img src="https://user-images.githubusercontent.com/59448872/209556091-fd0bcf9a-44e4-4b08-906f-a010496289f4.png" />
</p>




*İyi çalışmalar:)*


