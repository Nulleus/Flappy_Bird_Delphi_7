unit Unit2;

interface

uses
  Windows, Messages, SysUtils, Variants, Classes, Graphics, Controls, Forms,
  Dialogs, Buttons, Menus, ExtCtrls,Mmsystem, MPlayer;

type
  TForm2 = class(TForm)
    MainMenu1: TMainMenu;
    N1: TMenuItem;
    N2: TMenuItem;
    N3: TMenuItem;
    N4: TMenuItem;
    N5: TMenuItem;
    N6: TMenuItem;
    N7: TMenuItem;
    Image1: TImage;
    SpeedButton2: TSpeedButton;
    SpeedButton3: TSpeedButton;
    SpeedButton1: TSpeedButton;
    MediaPlayer1: TMediaPlayer;
    N8: TMenuItem;
    procedure SpeedButton1Click(Sender: TObject);
    procedure SpeedButton2Click(Sender: TObject);
    procedure N6Click(Sender: TObject);
    procedure N4Click(Sender: TObject);
    procedure SpeedButton3Click(Sender: TObject);
    procedure Timer1Timer(Sender: TObject);
    procedure FormCreate(Sender: TObject);
    procedure N7Click(Sender: TObject);
    procedure N2Click(Sender: TObject);
    procedure N8Click(Sender: TObject);
  private
    { Private declarations }
  public
    { Public declarations }
  end;

var
  Form2: TForm2;

implementation

uses Unit1, Unit3, Unit4, Unit5, Unit6;

{$R *.dfm}

procedure TForm2.SpeedButton1Click(Sender: TObject);
begin
Form1.SpeedButton1.Visible:=True;
Form1.Show;
end;

procedure TForm2.SpeedButton2Click(Sender: TObject);
begin
form3.Show;
end;

procedure TForm2.N6Click(Sender: TObject);
begin
Form4.Show;
end;

procedure TForm2.N4Click(Sender: TObject);
begin
Form3.Show;
end;

procedure TForm2.SpeedButton3Click(Sender: TObject);
begin
Application.Terminate;
end;

procedure TForm2.Timer1Timer(Sender: TObject);
begin
//PlaySound('1.wav', 0, SND_ASYNC and SND_LOOP);
end;

procedure TForm2.FormCreate(Sender: TObject);
begin
MediaPlayer1.FileName:='1.wav';
MediaPlayer1.Open;
MediaPlayer1.Play;
end;

procedure TForm2.N7Click(Sender: TObject);
begin
Form5.Show;
end;

procedure TForm2.N2Click(Sender: TObject);
begin
SpeedButton1.Click;
end;

procedure TForm2.N8Click(Sender: TObject);
begin
Form6.Show;
end;

end.
