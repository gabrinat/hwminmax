# hwminmax
//Напишите программу, которая находит минимальное и максимальное среди четных положительных чисел, записанных в файле, и выводит результат в другой файл. Учтите, что таких чисел может вообще не быть
var
    fin, fout: text;
    min, max, x: longint;

begin
    max := 0;
    min := 0;
    assign(fin, 'input.txt');
    assign(fout, 'output.txt');
    reset(fin);
    rewrite(fout);
    while not eof(fin) do
    begin
        readln(fin, x);
        if (x > 0) then
        begin
            if (x > max) then
            begin
                if (min = 0) then
                    min := x;
                max := x;
            end;
            if (x < min) then
                min := x;
        end;
    end;
    if not (max = 0) then
        writeln(fout, 'max = ', max)
    else
        writeln(fout, 'max = error');
    if not (min = 0) and not (min = max) then
        writeln(fout, 'min = ', min)
    else
        writeln(fout, 'min = error');
    close(fin);
    close(fout);
end.
