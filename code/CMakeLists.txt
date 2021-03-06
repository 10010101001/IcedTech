﻿# CMakeList.txt : CMake project for Darklight, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

include( PrecompiledHeader.cmake )
project(Darklight)

set(CMAKE_CXX_FLAGS "")

#Check to see if we are wanting a SDK project or a full engine project
Message("${CMAKE_CURRENT_SOURCE_DIR}/full_sdk_license.txt")#

#set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/../)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/../)
#set(CMAKE_VERBOSE_MAKEFILE ON)

# idLib files
if(WIN32)
	set(src_idlib
	./idlib/precompiled.cpp
	./idlib/precompiled.h
	./idlib/Base64.cpp
	./idlib/BitMsg.h
	./idlib/Base64.h
	./idlib/BitMsg.cpp
	./idlib/bv
	./idlib/CmdArgs.cpp
	./idlib/CmdArgs.h
	./idlib/containers
	./idlib/Dict.cpp
	./idlib/Dict.h
	./idlib/geometry
	./idlib/hashing
	./idlib/Heap.cpp
	./idlib/Heap.h
	./idlib/LangDict.cpp
	./idlib/LangDict.h
	./idlib/Lexer.cpp
	./idlib/Lexer.h
	./idlib/Lib.cpp
	./idlib/Lib.h
	./idlib/MapFile.cpp
	./idlib/MapFile.h
	./idlib/math
	./idlib/Parser.cpp
	./idlib/Parser.h
	./idlib/Str.cpp
	./idlib/Str.h
	./idlib/Swap.h
	./idlib/Timer.cpp
	./idlib/Timer.h
	./idlib/Token.cpp
	./idlib/Token.h
	./idlib/bv/Bounds.cpp
	./idlib/bv/Bounds.h
	./idlib/bv/Box.cpp
	./idlib/bv/Box.h
	./idlib/bv/Frustum.cpp
	./idlib/bv/Frustum.h
	./idlib/bv/Sphere.cpp
	./idlib/bv/Sphere.h
	./idlib/containers/Array.h
	./idlib/containers/BinSearch.h
	./idlib/containers/BTree.h
	./idlib/containers/HashIndex.cpp
	./idlib/containers/HashIndex.h
	./idlib/containers/HashTable.h
	./idlib/containers/Hierarchy.h
	./idlib/containers/LinkList.h
	./idlib/containers/List.h
	./idlib/containers/ListSTL.h
	./idlib/containers/PlaneSet.h
	./idlib/containers/Queue.h
	./idlib/containers/Sort.h
	./idlib/containers/Stack.h
	./idlib/containers/StaticList.h
	./idlib/containers/StrList.h
	./idlib/containers/StrPool.h
	./idlib/containers/VectorSet.h
	./idlib/geometry/DrawVert.cpp
	./idlib/geometry/DrawVert.h
	./idlib/geometry/JointTransform.cpp
	./idlib/geometry/JointTransform.h
	./idlib/geometry/Surface.cpp
	./idlib/geometry/Surface.h
	./idlib/geometry/Surface_Patch.cpp
	./idlib/geometry/Surface_Patch.h
	./idlib/geometry/Surface_Polytope.cpp
	./idlib/geometry/Surface_Polytope.h
	./idlib/geometry/Surface_SweptSpline.cpp
	./idlib/geometry/Surface_SweptSpline.h
	./idlib/geometry/TraceModel.cpp
	./idlib/geometry/TraceModel.h
	./idlib/geometry/Winding.cpp
	./idlib/geometry/Winding.h
	./idlib/geometry/Winding2D.cpp
	./idlib/geometry/Winding2D.h
	./idlib/hashing/CRC32.cpp
	./idlib/hashing/CRC32.h
	./idlib/hashing/MD4.cpp
	./idlib/hashing/MD4.h
	./idlib/hashing/MD5.cpp
	./idlib/hashing/MD5.h
	./idlib/math/Angles.cpp
	./idlib/math/Angles.h
	./idlib/math/Complex.cpp
	./idlib/math/Complex.h
	./idlib/math/Curve.h
	./idlib/math/Extrapolate.h
	./idlib/math/Float16.h
	./idlib/math/Interpolate.h
	./idlib/math/Lcp.cpp
	./idlib/math/Lcp.h
	./idlib/math/Math.cpp
	./idlib/math/Math.h
	./idlib/math/Matrix.cpp
	./idlib/math/Matrix.h
	./idlib/math/Ode.cpp
	./idlib/math/Ode.h
	./idlib/math/Plane.cpp
	./idlib/math/Plane.h
	./idlib/math/Pluecker.cpp
	./idlib/math/Pluecker.h
	./idlib/math/Polynomial.cpp
	./idlib/math/Polynomial.h
	./idlib/math/Quat.cpp
	./idlib/math/Quat.h
	./idlib/math/Random.h
	./idlib/math/Rotation.cpp
	./idlib/math/Rotation.h
	./idlib/math/Simd.cpp
	./idlib/math/Simd.h
	./idlib/math/Simd_Generic.cpp
	./idlib/math/Simd_Generic.h
	./idlib/math/Vector.cpp
	./idlib/math/Vector.h
	)
else() #linux
	set(src_idlib
	./idlib/precompiled.cpp
	./idlib/precompiled.h
	./idlib/Base64.cpp
	./idlib/BitMsg.h
	./idlib/Base64.h
	./idlib/BitMsg.cpp
	./idlib/bv
	./idlib/CmdArgs.cpp
	./idlib/CmdArgs.h
	./idlib/containers
	./idlib/Dict.cpp
	./idlib/Dict.h
	./idlib/geometry
	./idlib/hashing
	./idlib/Heap.cpp
	./idlib/Heap.h
	./idlib/LangDict.cpp
	./idlib/LangDict.h
	./idlib/Lexer.cpp
	./idlib/Lexer.h
	./idlib/Lib.cpp
	./idlib/Lib.h
	./idlib/MapFile.cpp
	./idlib/MapFile.h
	./idlib/math
	./idlib/Parser.cpp
	./idlib/Parser.h
	./idlib/Str.cpp
	./idlib/Str.h
	./idlib/Swap.h
	./idlib/Timer.cpp
	./idlib/Timer.h
	./idlib/Token.cpp
	./idlib/Token.h
	./idlib/bv/Bounds.cpp
	./idlib/bv/Bounds.h
	./idlib/bv/Box.cpp
	./idlib/bv/Box.h
	./idlib/bv/Frustum_gcc.cpp
	./idlib/bv/Frustum.cpp
	./idlib/bv/Frustum.h
	./idlib/bv/Sphere.cpp
	./idlib/bv/Sphere.h
	./idlib/containers/Array.h
	./idlib/containers/BinSearch.h
	./idlib/containers/BTree.h
	./idlib/containers/HashIndex.cpp
	./idlib/containers/HashIndex.h
	./idlib/containers/HashTable.h
	./idlib/containers/Hierarchy.h
	./idlib/containers/LinkList.h
	./idlib/containers/List.h
	./idlib/containers/ListSTL.h
	./idlib/containers/PlaneSet.h
	./idlib/containers/Queue.h
	./idlib/containers/Sort.h
	./idlib/containers/Stack.h
	./idlib/containers/StaticList.h
	./idlib/containers/StrList.h
	./idlib/containers/StrPool.h
	./idlib/containers/VectorSet.h
	./idlib/geometry/DrawVert.cpp
	./idlib/geometry/DrawVert.h
	./idlib/geometry/JointTransform.cpp
	./idlib/geometry/JointTransform.h
	./idlib/geometry/Surface.cpp
	./idlib/geometry/Surface.h
	./idlib/geometry/Surface_Patch.cpp
	./idlib/geometry/Surface_Patch.h
	./idlib/geometry/Surface_Polytope.cpp
	./idlib/geometry/Surface_Polytope.h
	./idlib/geometry/Surface_SweptSpline.cpp
	./idlib/geometry/Surface_SweptSpline.h
	./idlib/geometry/TraceModel.cpp
	./idlib/geometry/TraceModel.h
	./idlib/geometry/Winding.cpp
	./idlib/geometry/Winding.h
	./idlib/geometry/Winding2D.cpp
	./idlib/geometry/Winding2D.h
	./idlib/hashing/CRC32.cpp
	./idlib/hashing/CRC32.h
	./idlib/hashing/MD4.cpp
	./idlib/hashing/MD4.h
	./idlib/hashing/MD5.cpp
	./idlib/hashing/MD5.h
	./idlib/math/Angles.cpp
	./idlib/math/Angles.h
	./idlib/math/Complex.cpp
	./idlib/math/Complex.h
	./idlib/math/Curve.h
	./idlib/math/Extrapolate.h
	./idlib/math/Float16.h
	./idlib/math/Interpolate.h
	./idlib/math/Lcp.cpp
	./idlib/math/Lcp.h
	./idlib/math/Math.cpp
	./idlib/math/Math.h
	./idlib/math/Matrix.cpp
	./idlib/math/Matrix.h
	./idlib/math/Ode.cpp
	./idlib/math/Ode.h
	./idlib/math/Plane.cpp
	./idlib/math/Plane.h
	./idlib/math/Pluecker.cpp
	./idlib/math/Pluecker.h
	./idlib/math/Polynomial.cpp
	./idlib/math/Polynomial.h
	./idlib/math/Quat.cpp
	./idlib/math/Quat.h
	./idlib/math/Random.h
	./idlib/math/Rotation.cpp
	./idlib/math/Rotation.h
	./idlib/math/Simd.cpp
	./idlib/math/Simd.h
	./idlib/math/Simd_Generic.cpp
	./idlib/math/Simd_Generic.h
	./idlib/math/Vector.cpp
	./idlib/math/Vector.h
	)
endif()


set(src_game
	./game/Game_precompiled.cpp
	./game/Game_precompiled.h
	./game/bot/Bot.cpp
	./game/bot/Bot_Input.cpp
	./game/bot/Bot_char.cpp
	./game/bot/Bot_char.h
	./game/bot/Bot_goal.cpp
	./game/bot/Bot_goal.h
	./game/bot/Bot_weights.cpp
	./game/bot/Bot_weights.h
	./game/bot/Bot_weapons.cpp
	./game/bot/Bot_weapons.h
	./game/bot/Bot.h
	./game/bot/BotAI/BotAI.cpp
	./game/bot/BotAI/BotAI_respawn.cpp
	./game/bot/BotAI/BotAI_SeekLTG.cpp
	./game/bot/BotAI/BotAI.h
	./game/ReflectionProbe.cpp
	./game/ReflectionProbe.h
	./game/Game_navigation.cpp
	./game/Game_precompiled.cpp
	./game/Game_precompiled.h
	./game/Actor.cpp
	./game/Actor.h
	./game/AF.cpp
	./game/AF.h
	./game/AFEntity.cpp
	./game/AFEntity.h
	./game/anim
	./game/BrittleFracture.cpp
	./game/BrittleFracture.h
	./game/Camera.cpp
	./game/Camera.h
	./game/Entity.cpp
	./game/Entity.h
	./game/Fx.cpp
	./game/Fx.h
	./game/Game.def
	./game/Game.h
	./game/GameEdit.cpp
	./game/GameEdit.h
	./game/gamesys
	./game/Game_local.cpp
	./game/Game_local.h
	./game/Game_network.cpp
	./game/Game_parallel.cpp
	./game/Game_render.cpp
	./game/IK.cpp
	./game/IK.h
	./game/Item.cpp
	./game/Item.h
	./game/Light.cpp
	./game/Light.h
	./game/Misc.cpp
	./game/Misc.h
	./game/Moveable.cpp
	./game/Moveable.h
	./game/Mover.cpp
	./game/Mover.h
	./game/MultiplayerGame.cpp
	./game/MultiplayerGame.h
	./game/physics
	./game/Player.cpp
	./game/Player.h
	./game/PlayerIcon.cpp
	./game/PlayerIcon.h
	./game/PlayerView.cpp
	./game/PlayerView.h
	./game/Projectile.cpp
	./game/Projectile.h
	./game/Pvs.cpp
	./game/Pvs.h
	./game/script
	./game/SecurityCamera.cpp
	./game/SecurityCamera.h
	./game/SmokeParticles.cpp
	./game/SmokeParticles.h
	./game/Sound.cpp
	./game/Sound.h
	./game/Target.cpp
	./game/Target.h
	./game/Trigger.cpp
	./game/Trigger.h
	./game/Weapon.cpp
	./game/Weapon.h
	./game/weapons
	./game/WorldSpawn.cpp
	./game/WorldSpawn.h
	./game/anim/Anim.cpp
	./game/anim/Anim.h
	./game/anim/Anim_Blend.cpp
	./game/anim/Anim_Import.cpp
	./game/anim/Anim_Testmodel.cpp
	./game/anim/Anim_Testmodel.h
	./game/gamesys/Class.cpp
	./game/gamesys/Class.h
	./game/gamesys/DebugGraph.cpp
	./game/gamesys/DebugGraph.h
	./game/gamesys/Event.cpp
	./game/gamesys/Event.h
	./game/gamesys/NoGameTypeInfo.h
	./game/gamesys/SaveGame.cpp
	./game/gamesys/SaveGame.h
	./game/gamesys/SysCmds.cpp
	./game/gamesys/SysCmds.h
	./game/gamesys/SysCvar.cpp
	./game/gamesys/SysCvar.h
	./game/physics/Clip.cpp
	./game/physics/Clip.h
	./game/physics/Force.cpp
	./game/physics/Force.h
	./game/physics/Force_Constant.cpp
	./game/physics/Force_Constant.h
	./game/physics/Force_Drag.cpp
	./game/physics/Force_Drag.h
	./game/physics/Force_Field.cpp
	./game/physics/Force_Field.h
	./game/physics/Force_Spring.cpp
	./game/physics/Force_Spring.h
	./game/physics/Physics.cpp
	./game/physics/Physics.h
	./game/physics/Physics_Actor.cpp
	./game/physics/Physics_Actor.h
	./game/physics/Physics_AF.cpp
	./game/physics/Physics_AF.h
	./game/physics/Physics_Base.cpp
	./game/physics/Physics_Base.h
	./game/physics/Physics_Monster.cpp
	./game/physics/Physics_Monster.h
	./game/physics/Physics_Parametric.cpp
	./game/physics/Physics_Parametric.h
	./game/physics/Physics_Player.cpp
	./game/physics/Physics_Player.h
	./game/physics/Physics_RigidBody.cpp
	./game/physics/Physics_RigidBody.h
	./game/physics/Physics_Static.cpp
	./game/physics/Physics_Static.h
	./game/physics/Physics_StaticMulti.cpp
	./game/physics/Physics_StaticMulti.h
	./game/physics/Push.cpp
	./game/physics/Push.h
	./game/script/Script_Compiler.cpp
	./game/script/Script_Compiler.h
	./game/script/Script_Interpreter.cpp
	./game/script/Script_Interpreter.h
	./game/script/Script_Program.cpp
	./game/script/Script_Program.h
	./game/script/Script_Thread.cpp
	./game/script/Script_Thread.h
	./game/weapons/Weapon_bfg.cpp
	./game/weapons/Weapon_bfg.h
	./game/weapons/Weapon_chaingun.cpp
	./game/weapons/Weapon_chaingun.h
	./game/weapons/Weapon_fist.cpp
	./game/weapons/Weapon_fist.h
	./game/weapons/Weapon_flashlight.cpp
	./game/weapons/Weapon_flashlight.h
	./game/weapons/Weapon_machinegun.cpp
	./game/weapons/Weapon_machinegun.h
	./game/weapons/Weapon_pda.cpp
	./game/weapons/Weapon_pda.h
	./game/weapons/Weapon_pistol.cpp
	./game/weapons/Weapon_pistol.h
	./game/weapons/Weapon_plasmagun.cpp
	./game/weapons/Weapon_plasmagun.h
	./game/weapons/Weapon_rocketlauncher.cpp
	./game/weapons/Weapon_rocketlauncher.h
	./game/weapons/Weapon_shotgun.cpp
	./game/weapons/Weapon_shotgun.h

)

#Global Cmake Options
if(WIN32)
	add_definitions(-D_AFXDLL -D_WINDOWS -D_CRT_SECURE_NO_DEPRECATE)
else()
	#C and C++ flags
	set(CMAKE_C_FLAGS_DEBUG "-ggdb -D_DEBUG -O0 -fno-strict-aliasing -Woverloaded-virtual")
	set(CMAKE_CXX_FLAGS_DEBUG "-ggdb -D_DEBUG -O0 -Woverloaded-virtual")

	#add_compile_options(-Wall)

	#TODO fix warnings
	add_compile_options(-Wno-sign-compare)
	add_compile_options(-Wno-enum-compare)
	add_compile_options(-Wno-switch)
	add_compile_options(-Wno-format-security)
	add_compile_options(-Wno-unknown-pragmas) #pragma hdrstop is windows only.


	add_compile_options(-fno-strict-aliasing)
	#add_compile_options(-fvisibility=hidden) #dont export by default.
endif()

include_directories("${CMAKE_CURRENT_SOURCE_DIR}" )

# idLib project
add_library( idLib STATIC ${src_idlib} )
if(WIN32) #todo: fix this difference
	add_precompiled_header( idLib precompiled.h SOURCE_CXX ./idlib/precompiled.cpp )
else()
	add_precompiled_header( idLib ./idlib/precompiled.h SOURCE_CXX ./idlib/precompiled.cpp )
endif()
target_compile_definitions( idLib PRIVATE NAME=$<TARGET_FILE_NAME:idLib> )
target_include_directories( idLib PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}" "${CMAKE_CURRENT_SOURCE_DIR}/idlib/" )

if(WIN32)#todo: fix this difference
	set_target_properties(idLib PROPERTIES LINK_FLAGS "/PDB:\"idlib.pdb\"")
else()
	set_target_properties(idLib PROPERTIES POSITION_INDEPENDENT_CODE ON) #turn on -fPIC

endif()

# Game Project
add_library(game MODULE  ${src_game} )
target_compile_definitions(game PRIVATE GAME_DLL=1)
target_link_libraries(game idLib)
target_include_directories(game PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}" "${CMAKE_CURRENT_SOURCE_DIR}/game/")
if(WIN32)
	add_precompiled_header( game Game_precompiled.h  SOURCE_CXX ./game/Game_precompiled.cpp )
else()
	add_precompiled_header( game ./game/Game_precompiled.h  SOURCE_CXX ./game/Game_precompiled.cpp )
endif()

if(WIN32)
	set_target_properties(game PROPERTIES OUTPUT_NAME "gamex64" LINK_FLAGS "/PDB:\"Game.pdb\"")
else()
	set_target_properties(game PROPERTIES #POSITION_INDEPENDENT_CODE ON #turn on -fPIC
			OUTPUT_NAME "gamex64" # set game dll name
			PREFIX "")
endif()


#Include other projects
if(EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/full_sdk_license.txt")
	if(WIN32)
		Message("Including Tools...")
		add_definitions(-DID_ALLOW_TOOLS)
		include( Tools.cmake )
	else()
		Message("Tools not supported on Non-Windows...")
	endif()

	Message("Including Engine...")
	include( DarkEngine.cmake )
endif()

Message("Generated Projects.")