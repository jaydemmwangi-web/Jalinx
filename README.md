Galaxy Blaster

A complete, polished 2D arcade shooter using Pygame

Controls: Arrow keys to move, Space to shoot

import pygame import random import sys

------------------ Setup ------------------

pygame.init() WIDTH, HEIGHT = 800, 600 screen = pygame.display.set_mode((WIDTH, HEIGHT)) pygame.display.set_caption("Galaxy Blaster") clock = pygame.time.Clock() FONT = pygame.font.SysFont("arial", 24) BIGFONT = pygame.font.SysFont("arial", 48)

Colors

WHITE = (255, 255, 255) RED = (220, 60, 60) GREEN = (60, 220, 120) BLUE = (80, 160, 255) YELLOW = (255, 220, 80) BLACK = (0, 0, 0)

------------------ Player ------------------

player = pygame.Rect(WIDTH//2 - 20, HEIGHT - 70, 40, 40) player_speed = 6 lives = 3 score = 0

------------------ Bullets ------------------

bullets = [] bullet_speed = 10 shoot_cooldown = 250 last_shot = 0

------------------ Enemies ------------------

enemies = [] enemy_speed = 3 enemy_spawn_delay = 900 last_spawn = 0

------------------ Power-ups ------------------

powerups = [] powerup_timer = 0 rapid_fire = False

------------------ Functions ------------------

def draw_player(): pygame.draw.polygon(screen, BLUE, [ (player.centerx, player.top), (player.left, player.bottom), (player.right, player.bottom) ])

def draw_hud(): score_text = FONT.render(f"Score: {score}", True, WHITE) lives_text = FONT.render(f"Lives: {lives}", True, WHITE) screen.blit(score_text, (10, 10))# Jalinx
Game 
