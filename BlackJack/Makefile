# Nombre del programa
NAME       = BlackJack

# Flags de compilacion
FLAGS      = -Wall -Wextra -g -Ofast #-Werror

# Directorios
SRC_DIR    = ./Sources/
OBJ_DIR    = ./obj/
INC_DIR    = ./Headers/

# Archivos fuentes y objetos
SRC_FILES  = $(wildcard $(SRC_DIR)/*.c)
OBJ_FILES  = $(notdir $(SRC_FILES:.c=.o))

# Direcciones
SRC        = $(addprefix $(SRC_DIR), $(SRC_FILES))
OBJ        = $(addprefix $(OBJ_DIR), $(OBJ_FILES))

# Linkers
LNK        = -Ofast 

# Se compila el archivo binario (ejecutable).
all: obj $(NAME)

# Crea la carpeta donde estara los objetos.
obj:
	@mkdir -p $(OBJ_DIR)
$(OBJ_DIR)%.o: $(SRC_DIR)%.c
	@gcc $(FLAGS) -I $(INC_DIR) -o $@ -c $<

# Se compila los objetos con las librerias y archivos
$(NAME): $(OBJ)
	@echo "(ﾉ◕ヮ◕)ﾉ*:・ﾟ✧ Compilando, espere unos segundos..."
	@gcc $(OBJ) $(LNK) -lm -o $(NAME)
	@echo "(•̀ᴗ•́)و $(NAME) generado!"

# Remueve todos los archivos objetos
clean:
	@rm -Rf $(OBJ_DIR)
	@echo "¯\_(ツ)_/¯ Objectos eliminados!"

# Remueve todos los archivos objetos, binarios, y sus respectivas carpetas
fclean: clean
	@rm -f $(NAME)
	@echo "(╯°□°）╯︵ ┻━┻ $(NAME) removido!"

# Hace un re-make (como si se hubiera ejecutado Make por primera vez)
re: fclean all

# Le dice al make que estos nombre no son archivos
.PHONY: all clean fclean re