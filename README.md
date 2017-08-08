# ajaxfileupload
jquery ajax上传文件


$(document).ready(function() {
				$("#ctlBtn").click(function() {
					$.ajaxFileUpload({
						url: '/common/upload', //用于文件上传的服务器端请求地址
						secureuri: false, //是否需要安全协议，一般设置为false
						fileElementId: ['myFile','myFile1'], //文件上传域的ID
						dataType: 'json', //返回值类型 一般设置为json
						success: function(data, status) //服务器成功响应处理函数
							{
								alert(JSON.stringify(data))
							},
						error: function(data, status, e) //服务器响应失败处理函数
							{
								alert(e);
							}
					})
				});

			});
      
      
      <div id="uploader" class="wu-example">
			<!--用来存放文件信息-->
			<div id="thelist" class="uploader-list"></div>
			<div class="btns">
				<div id="clientFile">
					<input type="file" placeholder="请选择上传的文件" name="fileName" id="myFile" />

					<input type="file" placeholder="请选择上传的文件" name="fileName" id="myFile1" />
				</div>
				<button id="ctlBtn" class="btn btn-default">开始上传</button>
			</div>
		</div>
