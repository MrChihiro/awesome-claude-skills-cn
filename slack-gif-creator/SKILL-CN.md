---
name: slack-gif-creator
description: 用于创建针对 Slack 优化的动画 GIF 的工具包，带有针对尺寸限制的验证器和可组合的动画原语。当用户请求 Slack 的动画 GIF 或表情符号动画时，例如“为我制作一个 X 做 Y 的 Slack GIF”，此技能适用。
license: Complete terms in LICENSE.txt
---

# Slack GIF 创建器 - 灵活工具包

用于创建针对 Slack 优化的动画 GIF 的工具包。提供针对 Slack 限制的验证器、可组合的动画原语（摇动、弹跳、移动、万花筒）和可选的辅助实用程序。**根据需要应用这些工具以实现创意愿景。**

## Slack 的要求

Slack 根据用途对 GIF 有特定要求：

**消息 GIF：**
- 最大尺寸：~2MB
- 最佳尺寸：480x480
- 典型 FPS：15-20
- 颜色限制：128-256
- 持续时间：2-5s

**表情符号 GIF：**
- 最大尺寸：64KB（严格限制）
- 最佳尺寸：128x128
- 典型 FPS：10-12
- 颜色限制：32-48
- 持续时间：1-2s

**表情符号 GIF 具有挑战性** - 64KB 限制很严格。有帮助的策略：
- 限制总帧数为 10-15 帧
- 最多使用 32-48 种颜色
- 保持设计简单
- 避免渐变
- 频繁验证文件大小

## 工具包结构

此技能提供三种类型的工具：

1. **验证器** - 检查 GIF 是否符合 Slack 的要求
2. **动画原语** - 可组合的运动构建块（摇动、弹跳、移动、万花筒）
3. **辅助实用程序** - 常见需求的可选函数（文本、颜色、效果）

**在如何应用这些工具方面拥有完全的创作自由。**

## 核心验证器

为确保 GIF 符合 Slack 的约束，使用这些验证器：

```python
from core.gif_builder import GIFBuilder

# After creating your GIF, check if it meets requirements
builder = GIFBuilder(width=128, height=128, fps=10)
# ... add your frames however you want ...

# Save and check size
info = builder.save('emoji.gif', num_colors=48, optimize_for_emoji=True)

# The save method automatically warns if file exceeds limits
# info dict contains: size_kb, size_mb, frame_count, duration_seconds
```

**文件大小验证器**：
```python
from core.validators import check_slack_size

# Check if GIF meets size limits
passes, info = check_slack_size('emoji.gif', is_emoji=True)
# Returns: (True/False, dict with size details)
```

**尺寸验证器**：
```python
from core.validators import validate_dimensions

# Check dimensions
passes, info = validate_dimensions(128, 128, is_emoji=True)
# Returns: (True/False, dict with dimension details)
```

**完整验证**：
```python
from core.validators import validate_gif, is_slack_ready

# Run all validations
all_pass, results = validate_gif('emoji.gif', is_emoji=True)

# Or quick check
if is_slack_ready('emoji.gif', is_emoji=True):
    print("Ready to upload!")
```

## 动画原语

这些是可组合的运动构建块。将这些应用于任何对象的任何组合：

### 摇动 (Shake)
```python
from templates.shake import create_shake_animation

# Shake an emoji
frames = create_shake_animation(
    object_type='emoji',
    object_data={'emoji': '😱', 'size': 80},
    num_frames=20,
    shake_intensity=15,
    direction='both'  # or 'horizontal', 'vertical'
)
```

### 弹跳 (Bounce)
```python
from templates.bounce import create_bounce_animation

# Bounce a circle
frames = create_bounce_animation(
    object_type='circle',
    object_data={'radius': 40, 'color': (255, 100, 100)},
    num_frames=30,
    bounce_height=150
)
```

### 旋转 (Spin / Rotate)
```python
from templates.spin import create_spin_animation, create_loading_spinner

# Clockwise spin
frames = create_spin_animation(
    object_type='emoji',
    object_data={'emoji': '🔄', 'size': 100},
    rotation_type='clockwise',
    full_rotations=2
)

# Wobble rotation
frames = create_spin_animation(rotation_type='wobble', full_rotations=3)

# Loading spinner
frames = create_loading_spinner(spinner_type='dots')
```

### 脉冲 / 心跳 (Pulse / Heartbeat)
```python
from templates.pulse import create_pulse_animation, create_attention_pulse

# Smooth pulse
frames = create_pulse_animation(
    object_data={'emoji': '❤️', 'size': 100},
    pulse_type='smooth',
    scale_range=(0.8, 1.2)
)

# Heartbeat (double-pump)
frames = create_pulse_animation(pulse_type='heartbeat')

# Attention pulse for emoji GIFs
frames = create_attention_pulse(emoji='⚠️', num_frames=20)
```

### 淡入淡出 (Fade)
```python
from templates.fade import create_fade_animation, create_crossfade

# Fade in
frames = create_fade_animation(fade_type='in')

# Fade out
frames = create_fade_animation(fade_type='out')

# Crossfade between two emojis
frames = create_crossfade(
    object1_data={'emoji': '😊', 'size': 100},
    object2_data={'emoji': '😂', 'size': 100}
)
```

### 缩放 (Zoom)
```python
from templates.zoom import create_zoom_animation, create_explosion_zoom

# Zoom in dramatically
frames = create_zoom_animation(
    zoom_type='in',
    scale_range=(0.1, 2.0),
    add_motion_blur=True
)

# Zoom out
frames = create_zoom_animation(zoom_type='out')

# Explosion zoom
frames = create_explosion_zoom(emoji='💥')
```

### 爆炸 / 破碎 (Explode / Shatter)
```python
from templates.explode import create_explode_animation, create_particle_burst

# Burst explosion
frames = create_explode_animation(
    explode_type='burst',
    num_pieces=25
)

# Shatter effect
frames = create_explode_animation(explode_type='shatter')

# Dissolve into particles
frames = create_explode_animation(explode_type='dissolve')

# Particle burst
frames = create_particle_burst(particle_count=30)
```

### 摆动 / 抖动 (Wiggle / Jiggle)
```python
from templates.wiggle import create_wiggle_animation, create_excited_wiggle

# Jello wobble
frames = create_wiggle_animation(
    wiggle_type='jello',
    intensity=1.0,
    cycles=2
)

# Wave motion
frames = create_wiggle_animation(wiggle_type='wave')

# Excited wiggle for emoji GIFs
frames = create_excited_wiggle(emoji='🎉')
```

### 滑动 (Slide)
```python
from templates.slide import create_slide_animation, create_multi_slide

# Slide in from left with overshoot
frames = create_slide_animation(
    direction='left',
    slide_type='in',
    overshoot=True
)

# Slide across
frames = create_slide_animation(direction='left', slide_type='across')

# Multiple objects sliding in sequence
objects = [
    {'data': {'emoji': '🎯', 'size': 60}, 'direction': 'left', 'final_pos': (120, 240)},
    {'data': {'emoji': '🎪', 'size': 60}, 'direction': 'right', 'final_pos': (240, 240)}
]
frames = create_multi_slide(objects, stagger_delay=5)
```

### 翻转 (Flip)
```python
from templates.flip import create_flip_animation, create_quick_flip

# Horizontal flip between two emojis
frames = create_flip_animation(
    object1_data={'emoji': '😊', 'size': 120},
    object2_data={'emoji': '😂', 'size': 120},
    flip_axis='horizontal'
)

# Vertical flip
frames = create_flip_animation(flip_axis='vertical')

# Quick flip for emoji GIFs
frames = create_quick_flip('👍', '👎')
```

### 变形 / 变换 (Morph / Transform)
```python
from templates.morph import create_morph_animation, create_reaction_morph

# Crossfade morph
frames = create_morph_animation(
    object1_data={'emoji': '😊', 'size': 100},
    object2_data={'emoji': '😂', 'size': 100},
    morph_type='crossfade'
)

# Scale morph (shrink while other grows)
frames = create_morph_animation(morph_type='scale')

# Spin morph (3D flip-like)
frames = create_morph_animation(morph_type='spin_morph')
```

### 移动效果 (Move Effect)
```python
from templates.move import create_move_animation

# Linear movement
frames = create_move_animation(
    object_type='emoji',
    object_data={'emoji': '🚀', 'size': 60},
    start_pos=(50, 240),
    end_pos=(430, 240),
    motion_type='linear',
    easing='ease_out'
)

# Arc movement (parabolic trajectory)
frames = create_move_animation(
    object_type='emoji',
    object_data={'emoji': '⚽', 'size': 60},
    start_pos=(50, 350),
    end_pos=(430, 350),
    motion_type='arc',
    motion_params={'arc_height': 150}
)

# Circular movement
frames = create_move_animation(
    object_type='emoji',
    object_data={'emoji': '🌍', 'size': 50},
    motion_type='circle',
    motion_params={
        'center': (240, 240),
        'radius': 120,
        'angle_range': 360  # full circle
    }
)

# Wave movement
frames = create_move_animation(
    motion_type='wave',
    motion_params={
        'wave_amplitude': 50,
        'wave_frequency': 2
    }
)

# Or use low-level easing functions
from core.easing import interpolate, calculate_arc_motion

for i in range(num_frames):
    t = i / (num_frames - 1)
    x = interpolate(start_x, end_x, t, easing='ease_out')
    # Or: x, y = calculate_arc_motion(start, end, height, t)
```

### 万花筒效果 (Kaleidoscope Effect)
```python
from templates.kaleidoscope import apply_kaleidoscope, create_kaleidoscope_animation

# Apply to a single frame
kaleido_frame = apply_kaleidoscope(frame, segments=8)

# Or create animated kaleidoscope
frames = create_kaleidoscope_animation(
    base_frame=my_frame,  # or None for demo pattern
    num_frames=30,
    segments=8,
    rotation_speed=1.0
)

# Simple mirror effects (faster)
from templates.kaleidoscope import apply_simple_mirror

mirrored = apply_simple_mirror(frame, mode='quad')  # 4-way mirror
# modes: 'horizontal', 'vertical', 'quad', 'radial'
```

**要自由组合原语，请遵循这些模式：**
```python
# Example: Bounce + shake for impact
for i in range(num_frames):
    frame = create_blank_frame(480, 480, bg_color)

    # Bounce motion
    t_bounce = i / (num_frames - 1)
    y = interpolate(start_y, ground_y, t_bounce, 'bounce_out')

    # Add shake on impact (when y reaches ground)
    if y >= ground_y - 5:
        shake_x = math.sin(i * 2) * 10
        x = center_x + shake_x
    else:
        x = center_x

    draw_emoji(frame, '⚽', (x, y), size=60)
    builder.add_frame(frame)
```

## 辅助实用程序

这些是常见需求的可选助手。**根据需要使用、修改或替换这些自定义实现。**

### GIF 构建器 (组装与优化)

```python
from core.gif_builder import GIFBuilder

# Create builder with your chosen settings
builder = GIFBuilder(width=480, height=480, fps=20)

# Add frames (however you created them)
for frame in my_frames:
    builder.add_frame(frame)

# Save with optimization
builder.save('output.gif',
             num_colors=128,
             optimize_for_emoji=False)
```

关键特性：
- 自动颜色量化
- 重复帧删除
- Slack 限制的大小警告
- 表情符号模式（积极优化）

### 文本渲染

对于像表情符号这样的小 GIF，文本可读性具有挑战性。常见的解决方案包括添加轮廓：

```python
from core.typography import draw_text_with_outline, TYPOGRAPHY_SCALE

# Text with outline (helps readability)
draw_text_with_outline(
    frame, "BONK!",
    position=(240, 100),
    font_size=TYPOGRAPHY_SCALE['h1'],  # 60px
    text_color=(255, 68, 68),
    outline_color=(0, 0, 0),
    outline_width=4,
    centered=True
)
```

要实现自定义文本渲染，请使用 PIL 的 `ImageDraw.text()`，它对于较大的 GIF 效果很好。

### 颜色管理

专业外观的 GIF 通常使用连贯的调色板：

```python
from core.color_palettes import get_palette

# Get a pre-made palette
palette = get_palette('vibrant')  # or 'pastel', 'dark', 'neon', 'professional'

bg_color = palette['background']
text_color = palette['primary']
accent_color = palette['accent']
```

要直接使用颜色，请使用 RGB 元组 - 无论哪种方式适合用例。

### 视觉效果

冲击时刻的可选效果：

```python
from core.visual_effects import ParticleSystem, create_impact_flash, create_shockwave_rings

# Particle system
particles = ParticleSystem()
particles.emit_sparkles(x=240, y=200, count=15)
particles.emit_confetti(x=240, y=200, count=20)

# Update and render each frame
particles.update()
particles.render(frame)

# Flash effect
frame = create_impact_flash(frame, position=(240, 200), radius=100)

# Shockwave rings
frame = create_shockwave_rings(frame, position=(240, 200), radii=[30, 60, 90])
```

### 缓动函数

平滑运动使用缓动而不是线性插值：

```python
from core.easing import interpolate

# Object falling (accelerates)
y = interpolate(start=0, end=400, t=progress, easing='ease_in')

# Object landing (decelerates)
y = interpolate(start=0, end=400, t=progress, easing='ease_out')

# Bouncing
y = interpolate(start=0, end=400, t=progress, easing='bounce_out')

# Overshoot (elastic)
scale = interpolate(start=0.5, end=1.0, t=progress, easing='elastic_out')
```

可用缓动：`linear`, `ease_in`, `ease_out`, `ease_in_out`, `bounce_out`, `elastic_out`, `back_out` (过冲)，以及更多在 `core/easing.py` 中。

### 帧合成

如果需要，基本的绘图实用程序：

```python
from core.frame_composer import (
    create_gradient_background,  # Gradient backgrounds
    draw_emoji_enhanced,         # Emoji with optional shadow
    draw_circle_with_shadow,     # Shapes with depth
    draw_star                    # 5-pointed stars
)

# Gradient background
frame = create_gradient_background(480, 480, top_color, bottom_color)

# Emoji with shadow
draw_emoji_enhanced(frame, '🎉', position=(200, 200), size=80, shadow=True)
```

## 优化策略

当你的 GIF 太大时：

**对于消息 GIF (>2MB)：**
1. 减少帧数（降低 FPS 或缩短持续时间）
2. 减少颜色（128 → 64 色）
3. 减少尺寸（480x480 → 320x320）
4. 启用重复帧删除

**对于表情符号 GIF (>64KB) - 要积极：**
1. 限制总帧数为 10-12 帧
2. 最多使用 32-40 种颜色
3. 避免渐变（纯色压缩更好）
4. 简化设计（更少的元素）
5. 在保存方法中使用 `optimize_for_emoji=True`

## 示例合成模式

### 简单反应 (脉冲)
```python
builder = GIFBuilder(128, 128, 10)

for i in range(12):
    frame = Image.new('RGB', (128, 128), (240, 248, 255))

    # Pulsing scale
    scale = 1.0 + math.sin(i * 0.5) * 0.15
    size = int(60 * scale)

    draw_emoji_enhanced(frame, '😱', position=(64-size//2, 64-size//2),
                       size=size, shadow=False)
    builder.add_frame(frame)

builder.save('reaction.gif', num_colors=40, optimize_for_emoji=True)

# Validate
from core.validators import check_slack_size
check_slack_size('reaction.gif', is_emoji=True)
```

### 冲击动作 (弹跳 + 闪光)
```python
builder = GIFBuilder(480, 480, 20)

# Phase 1: Object falls
for i in range(15):
    frame = create_gradient_background(480, 480, (240, 248, 255), (200, 230, 255))
    t = i / 14
    y = interpolate(0, 350, t, 'ease_in')
    draw_emoji_enhanced(frame, '⚽', position=(220, int(y)), size=80)
    builder.add_frame(frame)

# Phase 2: Impact + flash
for i in range(8):
    frame = create_gradient_background(480, 480, (240, 248, 255), (200, 230, 255))

    # Flash on first frames
    if i < 3:
        frame = create_impact_flash(frame, (240, 350), radius=120, intensity=0.6)

    draw_emoji_enhanced(frame, '⚽', position=(220, 350), size=80)

    # Text appears
    if i > 2:
        draw_text_with_outline(frame, "GOAL!", position=(240, 150),
                              font_size=60, text_color=(255, 68, 68),
                              outline_color=(0, 0, 0), outline_width=4, centered=True)

    builder.add_frame(frame)

builder.save('goal.gif', num_colors=128)
```

### 组合原语 (移动 + 摇动)
```python
from templates.shake import create_shake_animation

# Create shake animation
shake_frames = create_shake_animation(
    object_type='emoji',
    object_data={'emoji': '😰', 'size': 70},
    num_frames=20,
    shake_intensity=12
)

# Create moving element that triggers the shake
builder = GIFBuilder(480, 480, 20)
for i in range(40):
    t = i / 39

    if i < 20:
        # Before trigger - use blank frame with moving object
        frame = create_blank_frame(480, 480, (255, 255, 255))
        x = interpolate(50, 300, t * 2, 'linear')
        draw_emoji_enhanced(frame, '🚗', position=(int(x), 300), size=60)
        draw_emoji_enhanced(frame, '😰', position=(350, 200), size=70)
    else:
        # After trigger - use shake frame
        frame = shake_frames[i - 20]
        # Add the car in final position
        draw_emoji_enhanced(frame, '🚗', position=(300, 300), size=60)

    builder.add_frame(frame)

builder.save('scare.gif')
```

## 哲学

此工具包提供构建块，而不是僵化的配方。要处理 GIF 请求：

1. **了解创意愿景** - 应该发生什么？情绪如何？
2. **设计动画** - 将其分解为阶段（预期、动作、反应）
3. **根据需要应用原语** - 摇动、弹跳、移动、效果 - 自由混合
4. **验证约束** - 检查文件大小，特别是对于表情符号 GIF
5. **如果需要，迭代** - 如果超出大小限制，减少帧/颜色

**目标是在 Slack 的技术限制内实现创作自由。**

## 依赖项

要使用此工具包，仅当这些依赖项尚不存在时才安装它们：

```bash
pip install pillow imageio numpy
```
