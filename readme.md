# Nice Popup

һ��򵥵ĵ����������֧�ֶ���ʽ�������Զ�������нϺ�֧�֡�

[Demo ��ʾ](https://ajccom.github.io/nicePopup)

-----------------------------------------------

## ʹ��˵��

Nice Popup ֧�� alert/confirm/dialog ���ֵ����㡣

#### Alert ������

Alter ������Ĭ��ӵ��һ�� ��ȷ���� ��ť�������رա��������е��İ���֧�� HTML������ͨ�� API ָ����

```javascript
nicePopup.alert.open('���Ƿ������ɵ')
```

��Ȼ������Ҳ����Ϊ alter ������ָ�����͡�

```javascript
nicePopup.alert.open('�������ൽ����', 'success')
```

��ʱ alert ���������ʾһ�� `type-icon` Ԫ�ء�

<br />

#### Confirm ������

Confirm ������Ĭ��ӵ��������ť����ȷ���� �� ��ȡ���������ȡ����رյ����㣬���ȷ����ִ��һ��ָ���Ļص�������

```javascript
nicePopup.confirm.open('��ȷ��Ҫ�ݳ���', function (popup) {
  console.log('I will rock you!')
  //�رյ�����
  popup.close()
})
```

<br />

#### Dialog ������

Dialog ��������Ҫҳ���ϴ��ڶ�Ӧ�� DOM Ԫ�ز���ʹ�á�Ϊ��Ҫ��Ԫ������� `nice-popup` ��

```HTML
<div id="popupEntity" class="nice-popup">������չʾ����</div>
```

�� Nice Popup ��ʼ���󣬾Ϳ���ͨ�����ַ�ʽ���� dialog��

```javascript
//���Ƚ��г�ʼ��
nicePopup.init()

//��һ�ַ�ʽ��ͨ�� selector �ַ������� dialog
nicePopup.dialog.open('#popupEntity')

//�ڶ��ַ�ʽ��ͨ�� DOMElement ���󵯳� dialog
nicePopup.dialog.open(document.getElementById('popupEntity'))
``` 

<br />

## ����˵��

���� | Ĭ��ֵ | ˵��
---- | ---- | ----
autoClose | false | �Ƿ��Զ��رգ�������д�Զ��رյ���ʱ������
effect | 'popin' | ��������ʾ/����Ч��
modal | true | �Ƿ���ģ̬��ģ̬�����һ�����ֲ���ʾ
closeable | true | �Ƿ���ʾ�رհ�ť

Alert, confirm ��������ѭ�������á�Dialog ���������ͨ�� `nicePoup.dialog.open` ������ָ̬���õ�����ʵ�������á�

<br />

#### �޸�����

Nice Popup �ṩ�޸�Ĭ�����÷�����

```javascript
nicePoup.config({
  closeable: false
})
```

ͨ�� `nicePoup.config` �����޸ĵ����ý����Ϊ�µ�Ĭ������

<br />

## API ˵��

### nicePoup

��ģ�黯����ʱ��Nice Popup �������ռ��� `nicePoup`��

����/���� | ���� | ˵��
---- | ---- | ----
alert | - | ���ԣ�alert ������
confirm | - | ���ԣ�confirm ������
dialog | - | ���ԣ�dialog ������
config | Config:Object | �������޸�Ĭ������
close | - | �������رյ�ǰһ��������
init | - | ��������ʼ��������

<br />

#### alert ����

Alert ����������� alert ��������� API��

����/���� | ���� | ˵��
---- | ---- | ----
open | Text:String[, Type:String] | ����һ�� alert ������

**ע�� alert ��û�� `close` ����������ʹ�� `nicePoup.close` �����رա�**

`open` �����ĵڶ������� Type ����Ϊ�ա������� `success/fail/wraning/wrong` ����״̬֮�⣬�û�����ʹ�������ַ�����Ϊ���������������״̬������Ҫ�� CSS �����ö�Ӧ��ʽ��

<br />

#### confirm ����

Confirm ����������� confirm ��������� API��Confirm �� alert ��֮ͬ��������ӵ��������ť����ȷ���� �� ��ȡ�����������û���� ��ȷ���� ʱ���ִ���û�ָ���ķ�����

����/���� | ���� | ˵��
---- | ---- | ----
open | Text:String[, Fn:Function] | ����һ�� confirm ������

**ע�� confirm Ҳû�� `close` ������������ Fn �����лᴫ��һ��ӵ�� `close` �����ĵ������������һ�� Popup ���ʵ����**

<br />

#### dialog ����

Dialog �� alert �� confirm ��̫��ͬ��û�й����Ĭ����ʽ��ֻ�ܵ����Ѵ��ڵ�ӵ�� `nice-popup` ���Ԫ�ء�

����/���� | ���� | ˵��
---- | ---- | ----
open | Selector:String|DOMElement:Object[, Config:Object] | ָ��һ��Ԫ����Ϊ dialog ���ݵ���
close | - | �رյ�ǰһ��������

**Dialog �� `close` �����õ�ͬ�� `nicePopup.close`��**

�� nicePopup ��ʼ����ʱ���Ѱ�Ҵ�ʱ�ĵ�������ӵ�� `nice-popup` ���Ԫ�ز�Ϊ��һһ���ɶ�Ӧ�� Popup ʵ����

<br />

## �Զ��嵯������

�������Ҫ��������������Ĭ�ϲ����е� `effect` Ϊ�ա�

```javascript
nicePopup.config({
  effect: ''
})
```

�����Ҫ������������������ָ��һ�������� `effect` ֮������ CSS�����磺

```javascript
nicePopup.config({
  effect: 'fade'
})
```

```CSS
.nice-popup.fade {
  animation-name: fadeIn;
  opacity: 1; top: 50%
}
.nice-popup.fade.reverse {
  animation-name: fadeOut;
  opacity: 0; top: -200%
}
@keyframes fadein {
  0% {top: 0px; opacity: 0;}
  100% {top: 0px; opacity: 1;}
}
@keyframes fadeout {
  0% {top: 0px; opacity: 1;}
  99% {top: 0px; opacity: 0;}
  100% {top: -5000px; opacity: 0;}
}
```

### ���е�ʵ��

����ʵ��ʹ���� `position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%)`��

���Ե��㴦����ʽ��ʱ����Ҫ�Դ˽�����

<br />

## Thanks

<br />















