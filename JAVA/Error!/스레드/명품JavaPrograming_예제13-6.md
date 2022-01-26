# 1. 'java' text를 가진 여러개의 레이블이 랜덤한 위치에 출력되지 않음

## 해결
layout을 null로 설정하지 않았기 때문.

```java
this.setLayout(null);
```

<br><br>

# 2. 'java' text를 가진 여러개의 레이블을 어떻게 구성하지?
## 해결
- 레이블의 위치를 갖는 벡터를 설정하고자 했지만 필요 없음
- while문을 돌 때마다 새로운 레이블을 생성하고 repaint 해주면 됨
    - 추가된 레이블을 다시 보이게 하기 위해서


```java
while(true) {
			int x = ((int)(Math.random()*contentPane.getWidth()));
			int y = ((int)(Math.random()*contentPane.getHeight()));
			JLabel label = new JLabel("java");
			label.setSize(80, 30);
			label.setLocation(x, y);
			contentPane.add(label);
			contentPane.repaint();
			
			try {
				Thread.sleep(300);
				
				if(flag) {
					contentPane.removeAll();
					label = new JLabel("finish");
					label.setSize(80, 30);
					label.setLocation(100, 100);
					
					label.setForeground(Color.RED);
					contentPane.add(label);
					contentPane.repaint();
					
					return; //스레드 종료
				}
			} catch (InterruptedException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			
		}
```
<br><br>

# 개선할 점
- 각 클래스의 역할 분리가 어려움. 연습 필요
- 답에서는 contentPane을 container에 담아서 이용했는데, JFrame을 사용하는 방법으로도 해보자.