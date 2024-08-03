# Django_study
学习django记录
# 设置一个文件夹为静态文件，然后可以给app引用里面的文件
在**setting.py**中
* BASE_DIR 定义为项目的根目录（即 manage.py 所在的目录）
`BASE_DIR = Path(__file__).resolve().parent.parent`
* STATIC_URL 是静态文件的 URL 路径前缀。静态文件在浏览器中的访问路径
`STATIC_URL = '/static/'`
* MEDIA_URL 是媒体文件的 URL 路径前缀。上传的文件在浏览器中的访问路径
`MEDIA_URL = '/media/'`
* MEDIA_ROOT 定义媒体文件在文件系统中的存储位置
`MEDIA_ROOT = BASE_DIR / 'media'`

在需要静态文件的**app的urls.py**中
* 如果 DEBUG 模式开启，添加静态和媒体文件的 URL 配置
* 这在开发环境中很有用，因为生产环境通常由服务器（如 Nginx）处理静态文件
`if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)`
* 在app的**views.py**中
`file_path = os.path.join(settings.MEDIA_ROOT, '模板文件.xlsx')`
![logo](https://github.com/user-attachments/assets/863c4e85-99fa-4079-aa52-0d4de64d285b)

