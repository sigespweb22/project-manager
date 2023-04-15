# Este script cria e faz o rastreamento de branches locais para cada branch remota listada no repositório GitLab. Depois de executar o loop for, você terá todas as branches remotas no seu repositório local.

* Windows
FOR /f "tokens=1,* delims=/" %G IN ('git branch -r ^| findstr /V "HEAD ->"') DO git branch --track %H %G/%H

* Mac ou Linux
FOR /f "tokens=1,* delims=/" %G IN ('git branch -r ^| grep -v "HEAD ->"') DO git branch --track %H %G/%H