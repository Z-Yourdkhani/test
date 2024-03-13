<!DOCTYPE html>
<html lang="fa">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>test</title>
    <script language="javascript" src="https://tarjomic.com/js/angular.min.js"></script>
    <script src="https://tarjomic.com/js/fileupload/ng-file-upload-shim.min.js"></script>
    <script src="https://tarjomic.com/js/fileupload/ng-file-upload.min.js"></script>
</head>

<body ng-controller="AudioRecorderController" ng-app="audioRecorderApp">

    <div>
        <button ng-click="startRecording()" ng-disabled="startButtonDisabled">شروع</button>
        <button ng-click="stopRecording()" ng-disabled="stopButtonDisabled">توقف</button>
        <audio ng-src="{{ audioUrl }}" controls></audio>
    </div>

    <form ng-submit="uploadAudio()" enctype="multipart/form-data">
        <input type="file" ng-model="audioFile" accept="audio/*" style="display: none;">
        <input type="submit" value="آپلود فایل وویس به سرور" ng-disabled="!audioFile">
    </form>



    <script>
        var app = angular.module('audioRecorderApp', ['ngFileUpload']);

        app.controller('AudioRecorderController', ['$scope', 'Upload', function ($scope, Upload) {
            $scope.audioFile = null;
            $scope.audioUrl = null;

            $scope.startButtonDisabled = false;
            $scope.stopButtonDisabled = true;

            let recorder;

            $scope.startRecording = function () {
                navigator.mediaDevices.getUserMedia({ audio: true })
                    .then(function (stream) {
                        recorder = RecordRTC(stream, {
                            type: 'audio',
                            mimeType: 'audio/webm'
                        });
                        recorder.startRecording();
                        $scope.$apply(function () {
                            $scope.startButtonDisabled = true;
                            $scope.stopButtonDisabled = false;
                        });
                    })
                    .catch(function (error) {
                        console.error('Error accessing microphone:', error);
                    });
            };

            $scope.stopRecording = function () {
                recorder.stopRecording(function () {
                    let blob = recorder.getBlob();
                    $scope.audioFile = new File([blob], 'recordedAudio.webm', { type: 'audio/webm' });
                    $scope.audioUrl = URL.createObjectURL(blob);
                    $scope.$apply(function () {
                        $scope.startButtonDisabled = false;
                        $scope.stopButtonDisabled = true;
                    });
                });
            };

            $scope.uploadAudio = function () {
                if ($scope.audioFile) {
                    Upload.upload({
                        url: "/upload.php", 
                        data: { file: $scope.audioFile }
                    }).then(function (response) {
                        console.log('Audio uploaded successfully!', response.data);
                 
                    }, function (error) {
                        console.error('Error uploading audio:', error);
                    });
                }
            };
        }]);
    </script>
</body>

</html>