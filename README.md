# Final

import pygame
import time
import random

pygame.init()

coulour_1 = (255,255,255)
coulour_2 = (255, 255,102)
colour_3 = (0,0,0)
coulour_4 = (213,200,80)
coulur_5 = (0, 255, 0)
colour_6 = (255,0,0)


add_caption = pygame.display.set_mode((box_len))

box_len = 900
box_height = 600
pygame.display.set_caption("Snake")

display style = pygame.font.SysFont("arial", 30, "bold")
score_font = pygame.font.SysFont("arial", 45, "bold")

def final_score(score):
    value = score_font.render("Enjoy the Snake Game--- Your Score is :" + str(score), True,colour_2)
    add_caption.blit(value, [0,0])

def make_snake(snake_block, list_snake):
    for x in list_snake:
        pygame.draw.rect(add_caption, coulour_3, [x[0], x[1], snake_block])

def display_msg)msg,color):
    mssg = display_style.render(msg, True, color)
    add_caption,blit(mssg, [box_len/6, box_height/3])

def game_start():
    game_over = False
    game_close = False

    value_x1 = box_len/2
    value_y1 = box_height/2

    new_x1 = 0
    new_y1 = 0

    list_snake = []
    snake_len = 1

    foodx_pos = round(random.randrange(0, box_len-snake_block)))
    foody_pos = round(random.randrange(0, box_height-snake_block))

    while not game_over:

        while game_close = True:
            add_caption.fill(colour_6)
            display_msg("You lost! Do you wanna play Again press C, else press J", coulour_4)
            final_score(snake_len-1)
            pygame.display.update()

            for event in pygame.event.get():
                if event.type == pygame.KEYDOWN:
                    if event.key == pygame.K_j:
                        game_over = True
                        game_close = False
                    if event.key == pygame,K_c:
                        game_start()
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    game_over = True
                if event. type == pygame.KEYDOWN:
                    if event.key == pygame.K_LEFT:
                        new_x1 = -snake_block
                        new_y1 = 0
                    elif event.key == pygame.K_RIGHT:
                        new_x1 = snake_block
                        new_y1 = 0 
                    

