unit Unit1;

{$mode objfpc}{$H+}

interface

uses
  Classes, SysUtils, FileUtil, TAGraph, TASeries, Forms, Controls, Graphics,
  Dialogs, StdCtrls, ExtCtrls;

type

  { TForm1 }

  TForm1 = class(TForm)
    Button1: TButton;
    Chart1: TChart;
    Chart1LineSeries1: TLineSeries;
    Edit1: TEdit;
    Edit2: TEdit;
    Edit3: TEdit;
    Image1: TImage;
    Label1: TLabel;
    Label2: TLabel;
    Label3: TLabel;
    Memo1: TMemo;
    procedure Button1Click(Sender: TObject);
  private
    { private declarations }
  public
    { public declarations }
  end;

var
  Form1: TForm1;

implementation

{$R *.lfm}

function F(x:real):real;
begin
F:=sqrt(x)-(sin(x)/cos(x))*(1-x);
end;

procedure TForm1.Button1Click(Sender: TObject);
var beg, last, eps, x: extended;
code, i: byte;
s: string;
begin
beg:=strtofloat(edit1.text);
last:=strtofloat(edit2.text);
eps:=strtofloat(edit3.text);
if beg>=last then messagedlg('Введите правильные значения', mtWarning, [mbOk], 0)
else
if (eps<0) and (eps>1) then messagedlg('Неправильная точность!', mtWarning, [mbOk], 0)
else

if cos(x)=0 then messagedlg('Деление на ноль!', mtWarning, [mbOk], 0)
else
begin
if (beg>last) or (F(beg)*F(last)>0) then messagedlg('Нет корней', mtWarning, [mbOk], 0);

memo1.lines.Clear;
memo1.lines.Add('     X'+'        '+'F(x)');
while ((last-beg)>eps) do
begin
  x:=(beg+last)/2;
if F(beg)*F(x)<=0 then last:=x
else
beg:=x;
Chart1LineSeries1.AddXY(x, f(x));
memo1.Lines.add(floattostrF(x, FFFixed, 6,4)+'  '+floattostrf(f(x), fffixed, 6,4));
end;
memo1.lines.add('Корень уравнения:'+floattostrF(x, FFFixed, 6,4));
end;
end;
end.

