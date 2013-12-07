program bathmos;
uses wincrt;
var a:array[1..10] of string;
    b:array[1..10,1..5] of integer;
    mo:array[1..10] of real;
    i,j:integer;
    n:string;
    c:real;

BEGIN

 {diabasma ma8htwn kai ba8mwn tous}

 for i:=1 to 10 do
 begin
  write('dwse onoma ma8hth: ');
  read(a[i]);
  for j:=1 to 5 do
  begin
   repeat
    write('dwse ba8mo ',j,' (apo 0 ws 10): ');
    read(b[i,j]);
     if b[i,j]>10 then
     begin
      writeln('dwse mirkotero noumero tou 10!');
     end;
    readln;
   until b[i,j]<11;
  end;
 end;

 {mesos oros}

 for i:=1 to 10 do
 begin
  mo[i]:=0;
   for j:=1 to 5 do
   begin
    mo[i]:=mo[i]+b[i,j]/5;
   end;
 end;

 {ta3inomish "FUSALIDA"}

 for i:=1 to 10 do
 begin
  for j:=10 downto i do
  begin
   if mo[i]<mo[j] then
   begin

    c:=mo[i];       {fusalida meswn orwn}
    mo[i]:=mo[j];
    mo[j]:=c;

    n:=a[i];        {fusalida onomatwn}
    a[i]:=a[j];
    a[j]:=n;

   end;
  end;
 end;

 {ti bgainei sthn o8onh}

 for i:=1 to 10 do
 begin
  writeln(i,' ',a[i],' ',mo[i]:4:2);
 end;

END.
