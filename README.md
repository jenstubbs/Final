# Final

import pygame
import time
import random

pygame.init()

white = (255,255,255)
black = (0,0,0)
green = (0, 255, 0)
red = (255,0,0)

snake_block = 20
snake_speed = 15

font_style = pygame.font.SysFont(None, 50)


box_len = 900
box_height = 600
pygame.display.set_caption("Snake")

display style = pygame.font.SysFont("arial", 30, "bold")
score_font = pygame.font.SysFont("arial", 45, "bold")

def our_snake(snake_block, snake_list):
    for x in snake_list:
        pygame.draw.circle(add_caption, green, (x[0] + snake_block // 2, x[1] + snake_block // 2), snake_block // 2)


def message(msg, color):
    mesg = font_style.render(msg, True, color)
    add_caption.blit(mesg, [box_width / 6, box_height / 3])

def gameLoop():
    game_over = False
    game_close = False

    x1 = box_len/2
    y1 = box_height/2

    new_x1 = 0
    new_y1 = 0

    list_snake = []
    snake_len = 1

foodx = round(random.randrange(0, box_width - snake_block) / 20.0) * 20.0
foody = round(random.randrange(0, box_height - snake_block) / 20.0) * 20.0

    while not game_over:
        while game_close:
            add_caption.fill(black)
           
            display_msg("You lost! Do you wanna play Again press C, else press J", red)
            pygame.display.update()
            
            for event in pygame.event.get():
                if event.type == pygame.KEYDOWN:
                    if event.key == pygame.K_q:
                        game_over = True
                        game_close = False
                    if event.key == pygame.K_c:
                        gameLoop()

        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                game_over = True
            if event.type == pygame.KEYDOWN:
                if event.key == pygame.K_LEFT:
                    x1_change = -snake_block
                    y1_change = 0
                elif event.key == pygame.K_RIGHT:
                    x1_change = snake_block
                    y1_change = 0
                elif event.key == pygame.K_UP:
                    y1_change = -snake_block
                    x1_change = 0
                elif event.key == pygame.K_DOWN:
                    y1_change = snake_block
                    x1_change = 0
            if value_x1>= box_len or x1<0 or y1>= box_height or y1<0:
                game_close = True

            x1 += x1_change
            y1 += y1_change
            add_caption.fill(black)
            pygame.draw.rectangle(add_caption, white [foodx,foody,snake_block,snake_block])
            snake_head = []
            snake_head.append(x1)
            snake_head.append(y1)
            list_snake.append(snake_head)
            if len(snake_list) > snake_len:
                del snake_list[0]
            for x in list_snake[:-1]:
                if x == snake_head:
                    game_close = True
            our_snake(snake_block, snake_list)
            pygame.display.update()

            if x1 == foodx and y1 == foody:
                foodx = round(random.randrange(0, box_width - snake_block) / 20.0) * 20.0
                foody = round(random.randrange(0 ,box_height - snake_block) / 20.0) * 20.0
               length_of_snake += 1
            pygame.time.Clock().tick(snake_speed)

            timer.tick(snake_speed)

        pygame.quit()
        quit()
game_start()

    


                    

