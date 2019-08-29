unit Unit1;

interface

uses
  Windows, Messages, SysUtils, Variants, Classes, Graphics, Controls, Forms,
  Dialogs, ExtCtrls, Menus, Buttons, StdCtrls, ComCtrls;

type
  TForm1 = class(TForm)
    Timer1: TTimer;
    Timer2: TTimer;
    Timer3: TTimer;
    SpeedButton1: TSpeedButton;
    StatusBar1: TStatusBar;
    SpeedButton2: TSpeedButton;
    SpeedButton3: TSpeedButton;
    procedure Level;
    procedure pipe;
    procedure pipe1;
    procedure bird;
    procedure FormKeyPress(Sender: TObject; var Key: Char);
    procedure Timer1Timer(Sender: TObject);
    procedure FormCreate(Sender: TObject);
    procedure FormMouseDown(Sender: TObject; Button: TMouseButton;
      Shift: TShiftState; X, Y: Integer);
    procedure Timer2Timer(Sender: TObject);
    procedure Timer3Timer(Sender: TObject);
    procedure FormMouseUp(Sender: TObject; Button: TMouseButton;
      Shift: TShiftState; X, Y: Integer);
    procedure SpeedButton1Click(Sender: TObject);
    procedure SpeedButton2Click(Sender: TObject);
    procedure SpeedButton3Click(Sender: TObject);
    procedure Timer4Timer(Sender: TObject);
  private
    a,b,abird,bbird:integer;
    kol_vo:integer;
    bx1,bx2,bx3,bx4,bx5,bx6,by1,by2,by3,by4,by5,by6,bw,bh:integer;
    px1,px2,px3,px4,px5,px6,py1,py2,py3,py4,py5,py6,px7,py7,pw,ph:integer;
    xcoll,ycoll,xcoll1,ycoll1:Boolean;//Столкновение коллизия
    stolknovenie,stolknovenie1:Boolean;
    schet:integer;
    Tekst:integer;
    { Private declarations }
  public
        Option_color:TColor;
    { Public declarations }
  end;

var
  Form1: TForm1;

implementation

uses Unit2, Unit3;

{$R *.dfm}
procedure TForm1.Level;
var BitMap:TBitmap;
begin
bitmap:=TBitMap.Create;
BitMap.LoadFromFile('level.bmp');
Canvas.Draw(0,0, BitMap);
end;

procedure TForm1.bird;
var BitMap:TBitmap;
begin
With Canvas do
begin
pen.Color:=clwhite;
Brush.Color:=clwhite;
Rectangle(bx1,by1+a,bx2,by2+a);
end;
bitmap:=TBitMap.Create;
BitMap.LoadFromFile('bird.bmp');
BitMap.Transparent:=True;
Canvas.Draw(bx1,by1+a, BitMap);
end;

procedure TForm1.pipe1;
begin
With Canvas do
begin
Brush.Color:=Option_color;
Rectangle(px5+b,py5,px6+b,py6);
end;
end;

procedure TForm1.pipe;
begin
With Canvas do
begin
Brush.Color:=Option_color;
Rectangle(px1+b,py1,px2+b,py2);
end;
end;

procedure TForm1.FormKeyPress(Sender: TObject; var Key: Char);
begin

if key=#32 then kol_vo:=0;

end;

procedure TForm1.Timer1Timer(Sender: TObject);
begin
a:=a+5;
if kol_vo<>3 then
begin
a:=a-30;
Inc(kol_vo);
end;

Refresh;
bird;
pipe;
pipe1;
end;

procedure TForm1.FormCreate(Sender: TObject);
begin
//Option_color:=clGreen;
schet:=0;
kol_vo:=3;
a:=0;
b:=0;
bx1:=10; // 1ая точка X птички
by1:=40; // 1ая точка Y птички
bx2:=100;// 2ая точка x птички
by2:=130; // 2ая точка y птички
px1:=380; // 1ая точка X трубы1
py1:=320; // 1ая точка Y трубы1
px2:=500; // 2ая точка X трубы1
py2:=640; // 2ая точка Y трубы 1
px5:=bx1; // 1ая точка X трубы2
py5:=0; // 1ая точка Y трубы2
px6:=bx4; // 2ая точка X трубы2
py6:=100; // 2ая точка Y трубы 2
end;

procedure TForm1.FormMouseDown(Sender: TObject; Button: TMouseButton;
  Shift: TShiftState; X, Y: Integer);
  var MyMouse: TMouse;
begin
//Caption:=IntToStr(X)+' '+IntToStr(Y);
end;

procedure TForm1.Timer2Timer(Sender: TObject);
var truba:integer;
    ast:string;
    buttonSelected : Integer;
    c:TBITMAP;
begin
Form1.Caption:=IntToStr(by2);
if (by2+a>=600) then
  begin
    Form1.Timer1.Enabled:=False;
    Form1.Timer2.Enabled:=False;
    Form1.Timer3.Enabled:=False;
    stolknovenie:=true;
    stolknovenie1:=true;
  end;
if (px2+b<=0) then
  begin
    SpeedButton1.Enabled:=True;
    Randomize;
    truba:=random(10)+1;
    //truba:=5;
    schet:=schet+1;
    b:=0;
    case truba of
      0:begin
          beep;
          py1:=520;
          py6:=320;
        end;
      1:begin
          beep;
          py1:=400;
          py6:=200;
        end;
      2:begin
          beep;
          py1:=450;
          py6:=250;
        end;
      3:begin
          beep;
          py1:=300;
          py6:=100;
        end;
      4:begin
          beep;
          py1:=520;
          py6:=320;
        end;
      5:begin
          beep;
          py1:=350;
          py6:=150;
        end;
      6:begin
          beep;
          py1:=420;
          py6:=220;
        end;
      7:begin
          beep;
          py1:=520;
          py6:=320;
        end;
      8:begin
          beep;
          py1:=550;
          py6:=350;
        end;
    end;
  end;
b:=b-10;
xcoll:=false;
ycoll:=false;
xcoll1:=false;
ycoll1:=false;
if (bx2>=px1+b) and (bx2 <= px3) then //Столкновение по x для нижней трубы1
  begin
    xcoll:=true;
  end;
if (by2+a>=py1) and (by2+a <= py3) then //Столкновение по y для нижней трубы1
  begin
    ycoll:=true;
  end;

if (bx4>=px7+b) and (bx4 <= px6) then //Столкновение по x для нижней трубы2
  begin
    xcoll1:=true;
  end;
if (by4+a<=py7) and (by4+a <= py6) then //Столкновение по y для нижней трубы2
  begin
    ycoll1:=true;
  end;
if (xcoll and ycoll)=true then
  begin
    stolknovenie1:=true;//Точка b2 столкнулась с точкой p1,p3
  end;
if (xcoll1 and ycoll1)=true then
  begin
    stolknovenie:=true;
  end;

if (stolknovenie=true) or (stolknovenie1=true) then
  begin
    Form1.Timer1.Enabled:=False;
    Form1.Timer2.Enabled:=False;
    Form1.Timer3.Enabled:=False;
    Refresh;
    bird;
    pipe;
    pipe1;
    ast:=InputBox('Игра завершена','Введите имя игрока','Безымянный');
    Form3.Table1.AppendRecord([nil,ast,schet]);
    Form3.Show;
    Refresh;
    SpeedButton1.Visible:=False;
    SpeedButton3.Visible:=True;
    SpeedButton2.Visible:=True;
    c:=TBitmap.Create;
    c.LoadFromFile('refresh.bmp');
    c.Transparent:=True;
    SpeedButton2.Glyph:=c;
  end;

end;


procedure TForm1.Timer3Timer(Sender: TObject);
begin
StatusBar1.Panels[0].Text:='Счет:'+IntToStr(schet);
bw:=bx2-bx1;
bh:=by2-by1;
bx3:=bx1;  //Нижняя левая точка птички X
by3:=by1+bh;// //Нижняя левая точка птички Y
bx4:=bx1+bw;
by4:=by1;
pw:=px2-px1;//ширина трубы
ph:=py2-py1;//высота трубы
px3:=px1;
py3:=py1+ph;
px4:=px1+pw;
py4:=py1;
px5:=px1; // 1ая точка X трубы2
px6:=px4; // 2ая точка X трубы2
px7:=px5;
py7:=py1;
end;

procedure TForm1.FormMouseUp(Sender: TObject; Button: TMouseButton;
  Shift: TShiftState; X, Y: Integer);
begin
kol_vo:=0;
end;

procedure TForm1.SpeedButton1Click(Sender: TObject);
begin
SpeedButton1.Visible:=False;
SpeedButton2.Visible:=False;
SpeedButton3.Visible:=False;
xcoll:=false;
ycoll:=false;
xcoll1:=false;
ycoll1:=false;
stolknovenie1:=false;
stolknovenie:=false;
schet:=0;
kol_vo:=3;
a:=0;
b:=0;
bx1:=10; // 1ая точка X птички
by1:=40; // 1ая точка Y птички
bx2:=100;// 2ая точка x птички
by2:=130; // 2ая точка y птички
px1:=380; // 1ая точка X трубы1
py1:=320; // 1ая точка Y трубы1
px2:=500; // 2ая точка X трубы1
py2:=640; // 2ая точка Y трубы 1
px5:=bx1; // 1ая точка X трубы2
py5:=0; // 1ая точка Y трубы2
px6:=bx4; // 2ая точка X трубы2
py6:=100; // 2ая точка Y трубы 2
schet:=0;
bw:=bx2-bx1;
bh:=by2-by1;
bx3:=bx1;  //Нижняя левая точка птички X
by3:=by1+bh;// //Нижняя левая точка птички Y
bx4:=bx1+bw;
by4:=by1;
pw:=px2-px1;//ширина трубы
ph:=py2-py1;//высота трубы
px3:=px1;
py3:=py1+ph;
px4:=px1+pw;
py4:=py1;
px5:=px1; // 1ая точка X трубы2
px6:=px4; // 2ая точка X трубы2
px7:=px5;
py7:=py1;
SpeedButton1.Visible:=false;
Form1.Timer1.Enabled:=True;
Form1.Timer2.Enabled:=True;
Form1.Timer3.Enabled:=True;
end;

procedure TForm1.SpeedButton2Click(Sender: TObject);
begin
SpeedButton1.Click;
end;

procedure TForm1.SpeedButton3Click(Sender: TObject);
begin
Application.Terminate;
end;

procedure TForm1.Timer4Timer(Sender: TObject);
var a:integer;
begin


end;

end.
