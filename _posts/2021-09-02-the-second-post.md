# Lập trình hướng đối tượng (OOP) trong C++

## Tính đóng gói (Encapsulation)
  **Khái niệm:** Tính đóng gói giúp ẩn đi các biến trong *class* và buộc phải thông qua các phương thức được class cung cấp mới có thể truy cập thay đổi giá trị biến từ bên ngoài.
  **Ví dụ:**
  ```cpp:
#include  <iostream>
#include  <string>

using  namespace  std;

class  Car{
		private:
			int  weight  =  500;
			string  color  =  "red";
		public:
			void  setColor(string  nColor){
				this->color  =  nColor;
			}
			string  getColor(){
				return  this->color;
			}
};

int  main()
{
	Car*  A  =  new  Car;
	cout<<A->getColor()<<endl;
	A->setColor("blue");
	cout<<A->getColor()<<endl;
	return  0;

}
  ```
  ***output***

    red
    blue

## Tính trừu tượng (Abstraction)
**Khái niệm:** Tính trừu tượng giúp class cha tạo ra một tiêu chuẩn chung (pure virtual function) buộc class con phải tuân theo. Định nghĩa lại đầy đủ các hàm đó thì mới có thể khởi tạo.
**Ví dụ:**
```cpp:
#include  <iostream>
#include  <string>

using  namespace  std;

class  Car{
	private:
		int  weight  =  500;
		string  color  =  "red";
	protected:
		int  maxSpeed  =  0;
	public:
		void  setColor(string  nColor){
			this->color  =  nColor;
		}
		virtual  void  setSpeed(int  speed) =  0;
		void  getSpeed(){
			cout<<"Car speed: "<<this->maxSpeed<<endl;
		}
};

class  ElectricCar : public  Car{
	void  setSpeed(int  speed){
		this->maxSpeed  =  speed;
		cout<<"New speed: "<<this->maxSpeed<<endl;
	}
	void  getSpeed(){
		cout<<"ElectricCar speed: "<<this->maxSpeed<<endl;
	}
};

int  main(){
	Car*  A  =  new  ElectricCar;
	A->setSpeed(100);
	A->getSpeed();
	return  0;
}
```
***output***

    New speed: 100
    ElectricCar speed: 100

## Tính đa hình (Polymorphism)


## Tính kế thừa (Inheritance)
