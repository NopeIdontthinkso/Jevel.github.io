A SIMPLE SPACE GAME IN UNITY
=

[click to play]()






A SIMPLE PLATFORM GAME MODEL IN PYTHON
=

![Capture](https://user-images.githubusercontent.com/87847280/229108499-74de3c2a-2133-4bc7-bbdf-0b8ed6223fa9.PNG)

Introduction
-

press 'z' to jump

press RIGHT and LEFT to move

several creatures can move in here

The Most Difficult Part
-
The most difficult part is making the physics simulation and collision detection
~~~python
class Player(Sprite):

    def on_update(self, dt):
        def move(speed,dir):
            self.position += dir*speed
            if self.is_touching_any_sprite_with_tag('ldtk_Ground'):
                while self.is_touching_any_sprite_with_tag('ldtk_Ground'):
                    self.position -= dir*speed/2
                if dir.y > 0:
                    self.yspeed = 0
                if dir.x > 0:
                    self.xspeed = 0
        self.xspeed *= self.levelset.drag
        self.yspeed += self.levelset.gravity
        move(self.xspeed, Point(1,0))
        move(self.yspeed, Point(0,1))
        if self.window.is_key_down(KeyCode.Z):
            self.yspeed = self.levelset.jumplimit
        if self.window.is_key_pressed(KeyCode.LEFT):
            if self.xspeed > -self.levelset.speedlimit:
                self.xspeed -= self.levelset.speed
        elif self.window.is_key_pressed(KeyCode.RIGHT):
            if self.xspeed < self.levelset.speedlimit:
                self.xspeed += self.levelset.speed
~~~

The Resources Used
-

VScode

Pycat

LDTK

IMG from Kenney.nl





