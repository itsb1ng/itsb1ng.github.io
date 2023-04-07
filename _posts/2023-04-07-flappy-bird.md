---
layout: post
title: Flappy Bird
subtitle: Flappy Bird using GoDot Engine
thumbnail-img: /assets/img/flappygame.png
share-img: /assets/img/flappygame.png
cover-img: /assets/img/flappycode.png
tags: [gdscript]
---

Introductory Project to GDScript and its Functionality

> Bird Movement

```gdscript
func _physics_process(delta):
	
	if position.y > 270 or position.y < -350:
		get_parent().end_game()
	
	if Input.is_action_just_pressed("ui_up"):
		velocity.y -= (delta * GRAVITY) * 35
		var motion = velocity * delta
		
		move_and_collide(motion)
	else:
		velocity.y += delta * GRAVITY

		var motion = velocity * delta
		move_and_collide(motion)
```

> Pipes Function

```gdscript
func _process(delta):
	var bottompipe = $BottomPipe
	var toppipe = $TopPipe
	toppipe.position.x -= delta * SPEED
	bottompipe.position.x -= delta * SPEED
	
	if toppipe.position.x <= 400 and canScore:
		canScore = false
		self.get_parent().change_score()
		
	
	if toppipe.position.x <= 100:
		reset()
		if get_parent().check_score() % 10 == 0:
			SPEED = SPEED + (SPEED * 0.3)
```

{: .box-error}
**Error:** Game in light development. Looking to further knowledge with RPG Game
