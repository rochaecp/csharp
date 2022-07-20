ifdef INPUT
arquivo=$(INPUT)
else
arquivo=entrada.txt
endif

app=bin/Debug/net5.0/TreinosBeecrowd

$(app): Program.cs 
	dotnet build

run: $(app)
	clear
	$(app) < $(arquivo)

clean:
	dotnet clean