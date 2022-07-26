# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: sesim <sesim@student.42seoul.kr>           +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2022/06/24 11:21:24 by sesim             #+#    #+#              #
#    Updated: 2022/07/18 09:29:44 by sesim            ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

CC = cc
CFLAGS = -g -Wall -Wextra -Werror
RM = rm -f

SRCS = fdf.c \
	   map_parser_1.c \
	   map_parser_2.c \
	   map_parser_3.c \
	   bresenham_1.c \
	   bresenham_2.c \
	   rotation.c \
	   projection.c \
	   liner.c \
	   key_func1.c \
	   key_func2.c

SRCS_BONUS = fdf_bonus.c \
			 map_parser_1_bonus.c \
			 map_parser_2_bonus.c \
			 map_parser_3_bonus.c \
			 bresenham_1_bonus.c \
			 bresenham_2_bonus.c \
			 rotation_bonus.c \
			 projection_bonus.c \
			 liner_bonus.c \
			 key_func1_bonus.c \
			 key_func2_bonus.c

OBJS = $(SRCS:.c=.o)
OBJS_BONUS = $(SRCS_BONUS:.c=.o)

ifdef WITH_BONUS
	OBJ_FILES = $(OBJS_BONUS)
else
	OBJ_FILES = $(OBJS)
endif

NAME = fdf

all : $(NAME)

bonus :
	make WITH_BONUS=1 all

$(NAME) : $(OBJ_FILES)
	make -C ../libft
	make -C ../mlx
	$(CC) $(CFLAGS) -L ../libft -l ft -L ../mlx -l mlx -framework OpenGL -framework AppKit $^ -o $@

clean :
	make -C ../libft clean
	make -C ../mlx clean
	$(RM) $(OBJS) $(OBJS_BONUS)

fclean : clean
	make -C ../libft fclean
	$(RM) $(NAME)

re :
	make fclean
	make all

.PHONY : bonus all clean fclean re
