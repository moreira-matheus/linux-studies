# Udemy: Terminal Linux

`pwd`: diretório atual (*present working directory*);



`cd <dir>`: muda diretório (*change directory*):

- `..`: diretório acima;
- `.`: diretório atual;
- `/`: diretório raiz.



`ls [<dir>]`: listar arquivos no diretório (*list*);



`clear`: limpa o terminal;



`mkdir <dir>`: cria diretório (*make directory*);



`echo <msg>`: escreve `<msg>`:

- `echo <msg> > <file>`: escreve `msg` em `<file>`;



`cp <src> <tgt>`: copia `<src>` para `<tgt>` (*copy*);



`mv <src> <tgt>`: move (ou renomeia, <u>quando no mesmo diretório</u>) `<src>` para `<tgt>` (*move*);



`rm <file>`: apaga `<file>`:

- Para diretórios, `rm -r <dir>` ou `rm -rf <dir>`;



`chmod <permission_code> <file>`: altera permissão de `<file>`  (*change mode*);



`chown <new_owner> <file>`: altera o dono de `<file>` (*change owner*);



**Permissões**:

- `ls -lh`: lista os arquivos da pasta atual, com suas permissões, seus grupos e seus tamanhos em KB (*human-readable*);

![](.\ls-lh.png)

- `d[3][3][3]`: diretório;
- `-rwx[3][3]`: permissões de leitura (`read`), escrita (`write`) e execução; referem-se às <u>permissões do dono</u>;
- `-[3]rwx[3]`: referem-se às <u>permissões do grupo do dono</u>;
- `-[3][3][rwx]`: referem-se às <u>permissões dos demais usuários</u>.

Permissão de leitura `r` = 4, de escrita `w` = 2 e de execução `x = 1`.

*Exemplos*:

- `chmod 777 <file>`: dá permissão total a `<file>`.
- `chmod 744 <file>`: dá permissão `rwx` ao dono e `rw` aos demais.
- `chmod 400 <file>`: dá permissão `r` ao dono e nenhuma aos demais.

`sudo <cmd>`: executa `<cmd>` como [root](https://en.wikipedia.org/wiki/Superuser).

- `sudo su`: muda para o usuário root.



`<cmd> &`: executa `<cmd>` em background (sem bloquear o terminal).



`top`: lista os programas abertos.

- `htop`:  lista os programas de forma legível (**precisa instalar**: `sudo apt-get install htop`).



`kill <pid>`: mata o processo de número `<pid>`.

- `kill <pid>`, `kill -s TERM <pid>`, `kill -TERM <pid>`, `kill -15 <pid>`: mandam [solicitação de terminação](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGTERM).
- `kill -s KILL <pid>`, `kill -KILL <pid>`, `kill -9 <pid>`: mandam sinal de [terminação imediata](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGKILL).



`vi <file>`: editor de texto nativo.

- `i`: modo inserção.
- `\Esc + :wq`: salva e sai.
- `\Esc + :x`: salva e sai [também](https://til.hashrocket.com/posts/2fdb6afb66-difference-between-wq-and-x).
- `\Esc + :q`: sai sem salvar.
- `\Esc + :q!`: força saída sem salvar.
- `\Esc + :<num>`: pula para linha `<num>`.
- `\Esc + \<txt>`: pula para a linha que contém `<abc>`.
- `dd`: apaga linha atual (modo de inserção).



**Shell script**:

`vi <file>.sh`: cria e abre `<file>.sh`.

*Exemplo*:

~~~shell
echo Olá, mundo!
ls
~~~

`bash <file>.sh`: executa `<file>.sh`.

Comentário funcional (adiciona o interpretador `bash`):

~~~shell
#!/bin/bash
echo Olá, mundo
ls
~~~

`chmod +x <file>.sh`: adiciona permissão de execução a `<file>.sh`.

`./<file>.sh`: executa `<file>.sh`.



`sudo shutdown -r now`: reinicia o computador.

`sudo shutdown -h now`: desliga o computador.

`exit`: sai do terminal.

