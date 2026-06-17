import pygame
import sys

pygame.init()

WIDTH = 1280
HEIGHT = 720

screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Escape Room")

# IMAGES

bg = pygame.image.load("Images/bg.jpg").convert()
door = pygame.image.load("Images/door.png").convert_alpha()
mirror_black = pygame.image.load("Images/mirror_black.png").convert_alpha()
mirror_white = pygame.image.load("Images/mirror_white.png").convert_alpha()
mirror2 = pygame.image.load("Images/mirror2.png").convert_alpha()
mirror_cracks = pygame.image.load("Images/mirror_cracks.png").convert_alpha()
board = pygame.image.load("Images/board.png").convert_alpha()
board_closeup = pygame.image.load("Images/board_closeup.jpg").convert_alpha()
mirror2_closeup = pygame.image.load("Images/mirror2_closeup.jpg").convert_alpha()
mirror_cracks_closeup = pygame.image.load("Images/mirror_cracks_closeup.png").convert_alpha()
left_arrow = pygame.image.load("Images/left_arrow.png").convert_alpha()
right_arrow = pygame.image.load("Images/right_arrow.png").convert_alpha()
mirror_black_closeup = pygame.image.load("Images/mirror_black_closeup.png").convert_alpha()
mirror_white_closeup = pygame.image.load("Images/mirror_white_closeup.png").convert_alpha()
door_closeup = pygame.image.load("Images/door_closeup.png").convert_alpha()
down_arrow = pygame.image.load("Images/down_arrow.png").convert_alpha()
drawer = pygame.image.load("Images/drawer.png").convert_alpha()
drawer_closeup = pygame.image.load("Images/drawer.jpg").convert_alpha()
drawer_1 = pygame.image.load("Images/drawer_1.png").convert_alpha()
drawer_2 = pygame.image.load("Images/drawer_2.png").convert_alpha()
drawer_3 = pygame.image.load("Images/drawer_3.png").convert_alpha()
drawer_1_open = pygame.image.load("Images/drawer_1_open.png").convert_alpha()
drawer_2_open = pygame.image.load("Images/drawer_2_open.png").convert_alpha()
drawer_3_open = pygame.image.load("Images/drawer_3_open.png").convert_alpha()
carpet = pygame.image.load("Images/carpet.png").convert_alpha()
carpet_closeup = pygame.image.load("Images/carpet_closeup.png").convert_alpha()
carpet_bent = pygame.image.load("Images/carpet_bent_closeup.png").convert_alpha()
inventory = pygame.image.load("Images/inventory.png").convert_alpha()
key = pygame.image.load("Images/key.png").convert_alpha()
key = pygame.image.load("Images/key.png").convert_alpha()
key_icon = pygame.transform.scale(key, (60, 60))
pencil = pygame.image.load("Images/pencil.png").convert_alpha()
pencil_icon = pygame.transform.scale(pencil, (60, 60))
eraser = pygame.image.load("Images/eraser.png").convert_alpha()
eraser_icon = pygame.transform.scale(eraser, (60, 60))
blindfold = pygame.image.load("Images/blindfold.png").convert_alpha()
blindfold_icon = pygame.transform.scale(blindfold, (60, 60))
win_screen = pygame.image.load("Images/win_screen.jpg").convert_alpha()

#SLOTS
slot1 = pygame.image.load("Images/slot1.png").convert_alpha()
slot2 = pygame.image.load("Images/slot2.png").convert_alpha()
slot3 = pygame.image.load("Images/slot3.png").convert_alpha()
slot4 = pygame.image.load("Images/slot4.png").convert_alpha()
slot5 = pygame.image.load("Images/slot5.png").convert_alpha()

#CARDS
A1_front = pygame.image.load("Images/A1_front.png").convert_alpha()
A2_front = pygame.image.load("Images/A2_front.png").convert_alpha()
B1_front = pygame.image.load("Images/B1_front.png").convert_alpha()
B2_front = pygame.image.load("Images/B2_front.png").convert_alpha()
C1_front = pygame.image.load("Images/C1_front.png").convert_alpha()
C2_front = pygame.image.load("Images/C2_front.png").convert_alpha()

A1_back = pygame.image.load("Images/A1_back.png").convert_alpha()
A2_back = pygame.image.load("Images/A2_back.png").convert_alpha()
B1_back = pygame.image.load("Images/B1_back.png").convert_alpha()
B2_back = pygame.image.load("Images/B2_back.png").convert_alpha()
C1_back = pygame.image.load("Images/C1_back.png").convert_alpha()
C2_back = pygame.image.load("Images/C2_back.png").convert_alpha()

#CHARACTER
character_1 = pygame.image.load("Images/character_1.png").convert_alpha()
character_2 = pygame.image.load("Images/character_2.png").convert_alpha()
character_3 = pygame.image.load("Images/character_3.png").convert_alpha()
character_4 = pygame.image.load("Images/character_4.png").convert_alpha()

# FONT

font = pygame.font.Font("fonts/messages.ttf", 25)

# GAME STATE
current_view = "room1"
inventory_items = []
key_visible = True
pencil_visible = True
eraser_visible = True
blindfold_visible = False
drawer1_open = False
drawer2_open = False
drawer3_open = False
drawer_locked = True 
selected_item = None
character = character_1
A1_flipped = False
A2_flipped = False
B1_flipped = False
B2_flipped = False
C1_flipped = False
C2_flipped = False
cards = 0
card1_name = None
card1_value = None
card2_name = None
card2_value = None

matches = 0

mirror_unlocked = False
# CLICKABLE AREAS

mirror_rect = mirror_black.get_rect(topleft=(114, 175))
door_rect = door.get_rect(topleft=(976, 195))
drawer_rect = drawer.get_rect(topleft=(490, 240))
mirror2_rect = mirror2.get_rect(topleft=(490, 150))
mirror2_closeup_rect = mirror2_closeup.get_rect(topleft=(500, 300))
down_arrow_rect = down_arrow.get_rect(midbottom=(640, 710))
left_arrow_rect = left_arrow.get_rect(midleft=(10, 360))
right_arrow_rect = right_arrow.get_rect(midright=(1270, 360))
door_closeup_rect = door_closeup.get_rect(topleft=(0, 0))
mirror_black_closeup_rect = mirror_black_closeup.get_rect(topleft=(0, 0))
drawer_closeup_rect = drawer_closeup.get_rect(topleft=(0, 0))
drawer_1_rect = drawer_1.get_rect(topleft=(428, 84))
drawer_2_rect = drawer_2.get_rect(topleft=(428, 300))
drawer_3_rect = drawer_3.get_rect(topleft=(428, 510))
drawer_1_open_rect = drawer_1_open.get_rect(topleft=(428, 84))
drawer_2_open_rect = drawer_2_open.get_rect(topleft=(428, 300))
drawer_3_open_rect = drawer_3_open.get_rect(topleft=(428, 510))
board_rect = board.get_rect(topleft=(485, 109))
carpet_rect = carpet.get_rect(topleft=(450, 557))
carpet_closeup_rect = carpet_closeup.get_rect(topleft=(0, 0))
carpet_bent_rect = carpet_bent.get_rect(topleft=(0, 0))
slot1_rect = slot1.get_rect(topleft=(420, 10))
slot2_rect = slot1.get_rect(topleft=(510, 10))
slot3_rect = slot1.get_rect(topleft=(600, 10))
slot4_rect = slot1.get_rect(topleft=(690, 10))
slot5_rect = slot1.get_rect(topleft=(780, 10))
key_rect = key.get_rect(topleft=(1097, 381))
pencil_rect = pencil.get_rect(topleft=(690, 86))
eraser_rect = eraser.get_rect(topleft=(690, 310))
character_rect = character.get_rect(topleft=(500, 300))
blindfold_rect = blindfold.get_rect(topleft=(690, 310))


A1_front_rect = A1_front.get_rect(topleft=(290, 150))
A2_front_rect = A2_front.get_rect(topleft=(570, 150))
B1_front_rect = B1_front.get_rect(topleft=(850, 150))
B2_front_rect = B2_front.get_rect(topleft=(290, 410))
C1_front_rect = C1_front.get_rect(topleft=(570, 410))
C2_front_rect = C2_front.get_rect(topleft=(850, 410))  # FIXED: was C1_front

A1_back_rect = A1_back.get_rect(topleft=(290, 150))
A2_back_rect = A2_back.get_rect(topleft=(570, 150))
B1_back_rect = B1_back.get_rect(topleft=(850, 150))
B2_back_rect = B2_back.get_rect(topleft=(290, 410))
C1_back_rect = C1_back.get_rect(topleft=(570, 410))
C2_back_rect = C2_back.get_rect(topleft=(850, 410))  # FIXED: was C1_back

# MESSAGES
show_door_message = False
show_mirror_message = False
show_mirror2_message = False
show_drawer_message = False
show_warning_message = False
message_time = 0
d_message1 = "The door is locked."
d_message2 = "There is no keyhole."
d_message3 = "I need to find another way out."
m_message1 = "I can't see my reflection."
mc_message1 = "That is me."
mc_message2 = "There is still something missing."
mc_message3 = "That is better."
mc_message4 = "I think I am ready now."
dr_message = "It is locked."
warning_message = "I can't use it yet"
mc_message = mc_message1

# FUNCTIONS
def mirror_lit():
    mirror_black = mirror_white
    mirror_black_closeup = mirror_white_closeup
def draw_message(message, x, y):
    text_surface = font.render(message, True, (0, 0, 0))
    screen.blit(text_surface, (x, y))

def draw_inventory():
    screen.blit(inventory, (0, 0))
    
    screen.blit(slot1, slot1_rect.topleft)
    screen.blit(slot2, slot2_rect.topleft)
    screen.blit(slot3, slot3_rect.topleft)
    screen.blit(slot4, slot4_rect.topleft)
    screen.blit(slot5, slot5_rect.topleft)

    draw_inventory_items()

def draw_room1():
    screen.blit(bg, (0, 0))
    screen.blit(door, door_rect.topleft)
    screen.blit(carpet, carpet_rect.topleft)
    screen.blit(mirror_black, mirror_rect.topleft)

    draw_inventory()
    screen.blit(left_arrow, left_arrow_rect.topleft)
    screen.blit(right_arrow, right_arrow_rect.topleft)

def draw_room2():
    screen.blit(bg, (0, 0))
    screen.blit(left_arrow, left_arrow_rect.topleft)
    screen.blit(right_arrow, right_arrow_rect.topleft)
    screen.blit(drawer, drawer_rect.topleft)
    draw_inventory()

def draw_room3():
    screen.blit(bg, (0, 0))
    screen.blit(left_arrow, left_arrow_rect.topleft)
    screen.blit(right_arrow, right_arrow_rect.topleft)
    screen.blit(mirror2, mirror2_rect.topleft)
    screen.blit(mirror_cracks, mirror2_rect.topleft)
    draw_inventory()

def draw_room4():
    screen.blit(bg, (0, 0))
    screen.blit(left_arrow, left_arrow_rect.topleft)
    screen.blit(right_arrow, right_arrow_rect.topleft)
    screen.blit(board, board_rect.topleft) 
    draw_inventory()

def draw_mirror_closeup():
    screen.blit(mirror_black_closeup, (0, 0))
    screen.blit(down_arrow, down_arrow_rect.topleft)
    draw_inventory()
    global show_mirror_message
    if show_mirror_message:
        draw_message(m_message1, 37, 31)
        current_time = pygame.time.get_ticks()
        if current_time - message_time > 5000:
            show_mirror_message = False
    

def draw_door_closeup():

    screen.blit(door_closeup, (0, 0))
    screen.blit(down_arrow, down_arrow_rect.topleft)
    draw_inventory()
    global show_door_message
    if show_door_message:
        draw_message(d_message1, 37, 31)
        draw_message(d_message2, 37, 61)
        draw_message(d_message3, 37, 91)
        current_time = pygame.time.get_ticks()
        if current_time - message_time > 5000:
            show_door_message = False

def draw_drawer_closeup():
    screen.blit(drawer_closeup, (0, 0))
    if drawer3_open:
        screen.blit (drawer_3_open, drawer_3_open_rect.topleft)
    else:
        screen.blit (drawer_3, drawer_3_rect.topleft)
    if drawer2_open:
        screen.blit (drawer_2_open, drawer_2_open_rect.topleft)
        if eraser_visible:
            screen.blit(eraser, eraser_rect.topleft)
    else:
        screen.blit (drawer_2, drawer_2_rect.topleft)
    if drawer1_open:
        screen.blit (drawer_1_open, drawer_1_open_rect.topleft)
        if pencil_visible:
            screen.blit(pencil, pencil_rect.topleft)
    else:
        screen.blit (drawer_1, drawer_1_rect.topleft)

    screen.blit(down_arrow, down_arrow_rect.topleft)

    global show_drawer_message
    if show_drawer_message:
        draw_message(dr_message, 37, 31)
        current_time = pygame.time.get_ticks()
        if current_time - message_time > 5000:
            show_drawer_message = False

    draw_inventory()


def draw_mirror2_closeup():
    screen.blit(mirror2_closeup, (0, 0))
    screen.blit(character, character_rect.topleft)
    screen.blit(mirror_cracks_closeup, (0, 0))
    screen.blit(down_arrow, down_arrow_rect.topleft)
    
    draw_inventory()

    global show_mirror2_message
    global show_warning_message
    if show_mirror2_message:
        draw_message(mc_message, 37, 31)
        current_time = pygame.time.get_ticks()
        if current_time - message_time > 5000:
            show_mirror2_message = False

    if show_warning_message:
        draw_message(warning_message, 37, 50)
        current_time = pygame.time.get_ticks()
        if current_time - message_time > 5000:
            show_warning_message = False

def draw_board_closeup():
    screen.blit(board_closeup, (0, 0))
    
    if blindfold_visible:
        screen.blit(blindfold, blindfold_rect.topleft)

    if not (A1_flipped and A2_flipped):
        if A1_flipped: screen.blit(A1_front, A1_front_rect.topleft)
        else: 
            screen.blit(A1_back, A1_back_rect.topleft)
        
        if A2_flipped: screen.blit(A2_front, A2_front_rect.topleft)
        else: 
            screen.blit(A2_back, A2_back_rect.topleft)

    
    if not (C1_flipped and C2_flipped):
        if C1_flipped: screen.blit(C1_front, C1_front_rect.topleft)
        else: 
            screen.blit(C1_back, C1_back_rect.topleft)
        
        if C2_flipped: screen.blit(C2_front, C2_front_rect.topleft)
        else: 
            screen.blit(C2_back, C2_back_rect.topleft)

    
    if not (B1_flipped and B2_flipped):
        if B1_flipped: screen.blit(B1_front, B1_front_rect.topleft)
        else: 
            screen.blit(B1_back, B1_back_rect.topleft)
        
        if B2_flipped: screen.blit(B2_front, B2_front_rect.topleft)
        else: 
            screen.blit(B2_back, B2_back_rect.topleft)

    screen.blit(down_arrow, down_arrow_rect.topleft)
    draw_inventory()

def draw_carpet_closeup():
    screen.blit(carpet_closeup, (0, 0))
    screen.blit(down_arrow, down_arrow_rect.topleft)
    draw_inventory()

def draw_carpet_bent():
    screen.blit(carpet_bent, (0, 0))
    screen.blit(down_arrow, down_arrow_rect.topleft)
    if key_visible:
        screen.blit(key, key_rect.topleft)
    draw_inventory()

def draw_win_screen():
    screen.blit(win_screen, (0, 0))

def inventory_add(found_thing):
    inventory_items.append(found_thing)

def draw_inventory_items():

    if len(inventory_items) > 0:
        item_rect = inventory_items[0].get_rect(center=slot1_rect.center)
        screen.blit(inventory_items[0], item_rect)
        if selected_item == inventory_items[0]:
            pygame.draw.rect(screen, (255, 255, 0), slot1_rect, 3)

    if len(inventory_items) > 1:
        item_rect = inventory_items[1].get_rect(center=slot2_rect.center)
        screen.blit(inventory_items[1], item_rect)
        if selected_item == inventory_items[1]:
            pygame.draw.rect(screen, (255, 255, 0), slot2_rect, 3)

    if len(inventory_items) > 2:
        item_rect = inventory_items[2].get_rect(center=slot3_rect.center)
        screen.blit(inventory_items[2], item_rect)
        if selected_item == inventory_items[2]:
            pygame.draw.rect(screen, (255, 255, 0), slot3_rect, 3)


    if len(inventory_items) > 3:
        item_rect = inventory_items[3].get_rect(center=slot4_rect.center)
        screen.blit(inventory_items[3], item_rect)
        if selected_item == inventory_items[3]:
            pygame.draw.rect(screen, (255, 255, 0), slot4_rect, 3)

    if len(inventory_items) > 4:
        item_rect = inventory_items[4].get_rect(center=slot5_rect.center)
        screen.blit(inventory_items[4], item_rect)
        if selected_item == inventory_items[4]:
            pygame.draw.rect(screen, (255, 255, 0), slot5_rect, 3)
    
# --------------------
# MAIN GAME LOOP
# --------------------

while True:

    for event in pygame.event.get():

        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

        if event.type == pygame.KEYDOWN:
            print(f"Key pressed: {event.key}")
            if event.key == pygame.K_F11:  # this needs to be indented inside KEYDOWN
                pygame.display.toggle_fullscreen()

        if event.type == pygame.MOUSEBUTTONDOWN:

            mouse_pos = pygame.mouse.get_pos()

            print(mouse_pos)

            if slot1_rect.collidepoint(mouse_pos):
                if len(inventory_items) > 0:
                    selected_item = inventory_items[0]

            elif slot2_rect.collidepoint(mouse_pos):
                if len(inventory_items) > 1:
                    selected_item = inventory_items[1]

            elif slot3_rect.collidepoint(mouse_pos):
                if len(inventory_items) > 2:
                    selected_item = inventory_items[2]

            elif slot4_rect.collidepoint(mouse_pos):
                if len(inventory_items) > 3:
                    selected_item = inventory_items[3]

            elif slot5_rect.collidepoint(mouse_pos):
                if len(inventory_items) > 4:
                    selected_item = inventory_items[4]

            # ROOM1

            if current_view == "room1":

                if mirror_rect.collidepoint(mouse_pos):
                     current_view = "mirror"

                elif door_rect.collidepoint(mouse_pos):
                    current_view = "door"

                elif left_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room2"

                elif right_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room4"

                elif carpet_rect.collidepoint(mouse_pos):
                    current_view = "carpet"

            # MIRROR VIEW

            elif current_view == "mirror":

                if down_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room1"

                elif mirror_black_closeup_rect.collidepoint(mouse_pos):
                    if mirror_unlocked:
                        current_view = "win_screen"
                    else:
                        show_mirror_message = True
                        message_time = pygame.time.get_ticks()

                

            # DOOR VIEW

            elif current_view == "door":

                if down_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room1"

                # Click anywhere on the door close-up
                elif door_closeup_rect.collidepoint(mouse_pos):
                    show_door_message = True
                    message_time = pygame.time.get_ticks()

            # ROOM 2 VIEW

            elif current_view == "room2":

                if right_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room1"

                elif left_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room3"

                elif drawer_rect.collidepoint(mouse_pos):
                    current_view = "drawer_closeup"

            # DRAWER VIEW

            elif current_view == "drawer_closeup":
                if down_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room2"

                elif drawer_1_rect.collidepoint(mouse_pos):
                    drawer1_open = not drawer1_open

                elif drawer_2_rect.collidepoint(mouse_pos):
                    if selected_item == key_icon and drawer_locked:
                        drawer2_open = not drawer2_open
                        drawer_locked = False
                        inventory_items.remove(key_icon)
                        selected_item = None
                    
                    elif not drawer_locked:
                        drawer2_open = not drawer2_open
                    else:
                        show_drawer_message = True
                        message_time = pygame.time.get_ticks()

                elif drawer_3_rect.collidepoint(mouse_pos):
                    drawer3_open = not drawer3_open
                
                if pencil_visible and drawer1_open:
                    if pencil_rect.collidepoint(mouse_pos):
                        inventory_add(pencil_icon)
                        pencil_visible = False

                if eraser_visible and drawer2_open:
                    if eraser_rect.collidepoint(mouse_pos):
                        inventory_add(eraser_icon)
                        eraser_visible = False

            # ROOM3 VIEW
            elif current_view == "room3":
                if right_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room2"

                elif left_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room4"

                elif mirror2_rect.collidepoint(mouse_pos):
                    current_view = "mirror2"

            # MIRROR2 VIEW
            elif current_view == "mirror2":
                if down_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room3"
                elif mirror2_closeup_rect.collidepoint(mouse_pos):
                    show_mirror2_message = True
                    message_time = pygame.time.get_ticks()
                    if selected_item == eraser_icon:
                        character = character_2
                        inventory_items.remove(eraser_icon)
                        selected_item = None
                        mc_message = mc_message2
                    elif selected_item == pencil_icon and character == character_1:
                        show_warning_message = True
                        message_time = pygame.time.get_ticks()
                    elif selected_item == pencil_icon and character == character_2:
                        character = character_3
                        inventory_items.remove(pencil_icon)
                        selected_item = None
                        mc_message = mc_message3

                    elif selected_item == blindfold_icon and character == character_1:
                        show_warning_message = True
                        message_time = pygame.time.get_ticks()

                    elif selected_item == blindfold_icon and character == character_2:
                        show_warning_message = True
                        message_time = pygame.time.get_ticks()

                    elif selected_item == blindfold_icon and character == character_3:
                        character = character_4
                        mirror_black = mirror_white       
                        mirror_black_closeup = mirror_white_closeup
                        inventory_items.remove(blindfold_icon)
                        selected_item = None
                        mc_message = mc_message4
                

            # ROOM4 VIEW
            elif current_view == "room4":
                if right_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room3"

                elif left_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room1"
                
                elif board_rect.collidepoint(mouse_pos):
                    current_view = "board"

            # BOARD VIEW
            elif current_view == "board":
                if down_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room4"
                
                else:
                    clicked_card_name = None
                    clicked_card_value = None


                    if A1_back_rect.collidepoint(mouse_pos) and not A1_flipped and not (A1_flipped and A2_flipped):
                        A1_flipped = True
                        clicked_card_name = "A1"
                        clicked_card_value = "a"

                    elif A2_back_rect.collidepoint(mouse_pos) and not A2_flipped and not (A1_flipped and A2_flipped):
                        A2_flipped = True
                        clicked_card_name = "A2"
                        clicked_card_value = "a"

                    elif B1_back_rect.collidepoint(mouse_pos) and not B1_flipped and not (B1_flipped and C2_flipped):
                        B1_flipped = True
                        clicked_card_name = "B1"
                        clicked_card_value = "b"

                    elif B2_back_rect.collidepoint(mouse_pos) and not B2_flipped and not (B2_flipped and C1_flipped):
                        B2_flipped = True
                        clicked_card_name = "B2"
                        clicked_card_value = "b"

                    elif C1_back_rect.collidepoint(mouse_pos) and not C1_flipped and not (B2_flipped and C1_flipped):
                        C1_flipped = True
                        clicked_card_name = "C1"
                        clicked_card_value = "c"

                    elif C2_back_rect.collidepoint(mouse_pos) and not C2_flipped and not (B1_flipped and C2_flipped):
                        C2_flipped = True
                        clicked_card_name = "C2"
                        clicked_card_value = "c"


                    if clicked_card_name is not None:

                        if card1_name is None:
                            card1_name = clicked_card_name
                            card1_value = clicked_card_value

                        elif clicked_card_name == card1_name:
                            pass

                        else:
                            if card1_value == clicked_card_value:
                                matches += 1
                                print(f"Match found! Total pairs completed: {matches}")

                                if matches == 3:
                                    blindfold_visible = True

                                card1_name = None
                                card1_value = None

                            else:

                                draw_board_closeup()
                                pygame.display.update()
                                pygame.time.wait(800)  # Pause 0.8 seconds so they can see it

                                if card1_name == "A1" or clicked_card_name == "A1": A1_flipped = False
                                if card1_name == "A2" or clicked_card_name == "A2": A2_flipped = False
                                if card1_name == "B1" or clicked_card_name == "B1": B1_flipped = False
                                if card1_name == "B2" or clicked_card_name == "B2": B2_flipped = False
                                if card1_name == "C1" or clicked_card_name == "C1": C1_flipped = False
                                if card1_name == "C2" or clicked_card_name == "C2": C2_flipped = False

                                card1_name = None
                                card1_value = None

                    if blindfold_visible and blindfold_rect.collidepoint(mouse_pos):
                        inventory_add(blindfold_icon)
                        blindfold_visible = False    

            # CARPET VIEW
            elif current_view == "carpet":
                if down_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room1"
                elif carpet_closeup_rect.collidepoint(mouse_pos):
                    current_view = "carpet_bent"

            elif current_view == "carpet_bent":
                if key_visible:
                    if key_rect.collidepoint(mouse_pos):
                        inventory_add(key_icon)
                        key_visible = False
                if carpet_bent_rect.collidepoint(mouse_pos):
                    current_view = "carpet"

                elif down_arrow_rect.collidepoint(mouse_pos):
                    current_view = "room1"
            if character == character_4:
                mirror_unlocked = True
            
    screen.fill((50, 50, 50))

    if current_view == "room1":
        draw_room1()

    elif current_view == "mirror":
        draw_mirror_closeup()

    elif current_view == "door":
        draw_door_closeup()

    elif current_view == "room2":
        draw_room2()
    
    elif current_view == "drawer_closeup":
        draw_drawer_closeup()

    elif current_view == "room3":
        draw_room3()

    elif current_view == "mirror2":
        draw_mirror2_closeup()

    elif current_view == "room4":
        draw_room4()

    elif current_view == "board":
        draw_board_closeup()

    elif current_view == "carpet":
        draw_carpet_closeup()

    elif current_view == "carpet_bent":
        draw_carpet_bent() 

    elif current_view == "win_screen":
        draw_win_screen()  


    pygame.display.update()
