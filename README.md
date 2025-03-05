import pgzrun,random
WIDTH=1000
HEIGHT=800
TITLE="I am iron man"
message=""
ironman=Actor("ironman")
ironman.pos=WIDTH/2,HEIGHT/2

def draw():
    screen.clear()
    ironman.draw()
    screen.draw.text(message, center=(WIDTH/2,50),fontsize=30)
    place_ironman()
    print("hi")
def place_ironman():
    ironman.x=random.randint(50,WIDTH-50)
    ironman.y=random.randint(50,HEIGHT-50)

def on_mouse_down(pos):
    global message
    print(pos)
    if ironman.collidepoint(pos):
        place_ironman()
        message="target_engaged"
    else:
        message="target_missed"


pgzrun.go()
