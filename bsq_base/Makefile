# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: ichinoseyuuki <ichinoseyuuki@student.42    +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/01/28 13:12:23 by louisnop          #+#    #+#              #
#    Updated: 2023/08/07 13:47:35 by ichinoseyuu      ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

CC = gcc
CFLAGS = -Wall -Wextra -Werror
TARGET = bsq

SRCS_DIR = srcs
OBJS_DIR = objs
SRCS = main.c ft_puts.c ft_utility.c ft_strdup.c ft_strjoin.c ft_split.c ft_atoi.c ft_info.c ft_validate_map.c makesquare2.c helpmakesquare.c
OBJS = $(addprefix $(OBJS_DIR)/, $(SRCS:.c=.o))

all: $(TARGET)

$(TARGET): $(OBJS)
	$(CC) $(CFLAGS) -o $@ $(OBJS)

$(OBJS_DIR)/%.o: $(SRCS_DIR)/%.c
	mkdir -p $(OBJS_DIR)
	$(CC) $(CFLAGS) -c $< -o $@

.PHONY: all clean re
clean:
	-rm -f $(OBJS)

fclean:
	-rm -f $(TARGET) $(OBJS)

re: fclean all

t: re clean $(TARGET)
	perl make_map.pl 60 30 2  > example_map ; ./$(TARGET) example_map
