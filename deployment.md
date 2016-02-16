# ssh + tmux
Para desplegar servidores via ssh (remoto) uno puede correr los comandos directametne en una terminar ssh. El problema es que el proceso vive mientras la conexion se mantenga. Si mi intención es que el Job siga  corriendo independientemente de la terminal remota que lo inicia puedo recurrir a herramientas como tmux / screen o nohup.
Por lo que probé y leí la más adecuada es tmux.

Tmux: te permite iniciar consolas virtuales dentro de ssh y detachearlas. El paso a paso es
1. Conexion ssh
2. tmux (me abre un terminal virtual en mismo directorio)
3. Inicio el trabajo ej: rails s
4. Crtl + b , d -> con ese comando salgo de tmux y vuelvo a la pantalla 1
5. repito el proceso tantas veces como trabajos tenga que iniciar
6. tmux ls -> me detalla los trabajos corriendo
7. tmux a -t 0 -> me recupera la sesion 0
