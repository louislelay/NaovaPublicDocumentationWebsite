.. _config:

Ajouter la représentation au fichier de configuration
=====================================================

Dans ce tutoriel, nous allons voir comment ajouter la nouvelle représentation au fichier de configuration, 
en utilisant toujours le cas précis de la détection d’un objet rouge via la caméra.

Le code
-------

.. dropdown:: Extrait du fichier de configuration  
   :icon: code

   .. code-block:: cfg
      :emphasize-lines: 33

      defaultRepresentations = [
          GoalPostsPercept,
          ReplayWalkRequestGenerator,
      ];
      threads = [
          {
              name = Upper;
              priority = 0;
              debugReceiverSize = 2800000;
              debugSenderSize = 5200000;
              debugSenderInfrastructureSize = 100000;
              executionUnit = Perception;
              representationProviders = [
                  {representation = OtherFieldBoundary; provider = LowerProvider;},
                  {representation = OtherGoalPostsPercept; provider = LowerProvider;},
                  {representation = OtherObstaclesPerceptorData; provider = LowerProvider;},

                  {representation = AutoExposureWeightTable; provider = AutoExposureWeightTableProvider;},
                  {representation = BallPercept; provider = BallPerceptor;},
                  {representation = BallSpecification; provider = ConfigurationDataProvider;},
                  {representation = BallSpots; provider = BallSpotsProvider;},
                  {representation = BodyContour; provider = BodyContourProvider;},
                  {representation = CameraImage; provider = CameraProvider;},
                  {representation = CameraInfo; provider = CameraProvider;},
                  {representation = CameraIntrinsics; provider = CameraProvider;},
                  {representation = CameraMatrix; provider = CameraMatrixProvider;},
                  {representation = CameraSettings; provider = ConfigurationDataProvider;},
                  {representation = CameraStatus; provider = CameraProvider;},
                  {representation = CirclePercept; provider = LinePerceptor;},
                  {representation = CNSImage; provider = CNSImageProvider;},
                  {representation = CNSPenaltyMarkRegions; provider = PenaltyMarkRegionsProvider;},
                  {representation = CNSRegions; provider = CNSRegionsProvider;},
                  {representation = ColorDetect; provider = ColorDetector;},
                  {representation = ColorScanLineRegionsHorizontal; provider = ScanLineRegionizer;},
                  {representation = ColorScanLineRegionsVerticalClipped; provider = ScanLineRegionizer;},  
                  {representation = ECImage; provider = ECImageProvider;},
                  {representation = FieldBoundary; provider = FieldBoundaryProvider;},
                  {representation = FieldDimensions; provider = ConfigurationDataProvider;},
                  {representation = FieldLineIntersections; provider = FieldLinesProvider;},
                  {representation = FieldLines; provider = FieldLinesProvider;},
                  {representation = FrameInfo; provider = CameraProvider;},
                  {representation = ImageCoordinateSystem; provider = CoordinateSystemProvider;},
                  {representation = IntersectionsPercept; provider = IntersectionsProvider;},
                  {representation = JerseyClassifier; provider = JerseyClassifierProvider;},
                  {representation = JPEGImage; provider = CameraProvider;},
                  {representation = LinesPercept; provider = LinePerceptor;},
                  {representation = ObstaclesFieldPercept; provider = PlayersDeeptector;},
                  {representation = ObstaclesImagePercept; provider = PlayersDeeptector;},
                  {representation = ObstaclesPerceptorData; provider = PlayersDeeptector;},
                  {representation = PenaltyMarkPercept; provider = PenaltyMarkPerceptor;},
                  {representation = PenaltyMarkRegions; provider = PenaltyMarkRegionsProvider;},
                  {representation = RelativeFieldColors; provider = RelativeFieldColorsProvider;},
                  {representation = RelativeFieldColorsParameters; provider = ConfigurationDataProvider;},
                  {representation = RobotCameraMatrix; provider = RobotCameraMatrixProvider;},
                  {representation = RobotDimensions; provider = ConfigurationDataProvider;},
                  {representation = ScanGrid; provider = ScanGridProvider;},
              ];
          }, {
              name = Lower;
              priority = 0;
              debugReceiverSize = 1000000;
              debugSenderSize = 2000000;
              debugSenderInfrastructureSize = 100000;
              executionUnit = Perception;
              representationProviders = [
                  {representation = OtherFieldBoundary; provider = UpperProvider;},
                  {representation = OtherGoalPostsPercept; provider = UpperProvider;},
                  {representation = OtherObstaclesPerceptorData; provider = UpperProvider;},

                  {representation = AutoExposureWeightTable; provider = AutoExposureWeightTableProvider;},
                  {representation = BallPercept; provider = BallPerceptor;},
                  {representation = BallSpecification; provider = ConfigurationDataProvider;},
                  {representation = BallSpots; provider = BallSpotsProvider;},
                  {representation = BodyContour; provider = BodyContourProvider;},
                  {representation = CameraImage; provider = CameraProvider;},
                  {representation = CameraInfo; provider = CameraProvider;},
                  {representation = CameraIntrinsics; provider = CameraProvider;},
                  {representation = CameraMatrix; provider = CameraMatrixProvider;},
                  {representation = CameraSettings; provider = ConfigurationDataProvider;},
                  {representation = CameraStatus; provider = CameraProvider;},
                  {representation = CirclePercept; provider = LinePerceptor;},
                  {representation = CNSImage; provider = CNSImageProvider;},
                  {representation = CNSPenaltyMarkRegions; provider = PenaltyMarkRegionsProvider;},
                  {representation = CNSRegions; provider = CNSRegionsProvider;},
                  {representation = ColorScanLineRegionsHorizontal; provider = ScanLineRegionizer;},
                  {representation = ColorScanLineRegionsVerticalClipped; provider = ScanLineRegionizer;},
                  {representation = ECImage; provider = ECImageProvider;},
                  {representation = FieldBoundary; provider = FieldBoundaryProvider;},
                  {representation = FieldDimensions; provider = ConfigurationDataProvider;},
                  {representation = FieldLineIntersections; provider = FieldLinesProvider;},
                  {representation = FieldLines; provider = FieldLinesProvider;},
                  {representation = FrameInfo; provider = CameraProvider;},
                  {representation = ImageCoordinateSystem; provider = CoordinateSystemProvider;},
                  {representation = IntersectionsPercept; provider = IntersectionsProvider;},
                  {representation = JerseyClassifier; provider = JerseyClassifierProvider;},
                  {representation = JPEGImage; provider = CameraProvider;},
                  {representation = LinesPercept; provider = LinePerceptor;},
                  {representation = ObstaclesFieldPercept; provider = PlayersDeeptector;},
                  {representation = ObstaclesImagePercept; provider = PlayersDeeptector;},
                  {representation = ObstaclesPerceptorData; provider = PlayersDeeptector;},
                  {representation = PenaltyMarkPercept; provider = PenaltyMarkPerceptor;},
                  {representation = PenaltyMarkRegions; provider = PenaltyMarkRegionsProvider;},
                  {representation = RelativeFieldColors; provider = RelativeFieldColorsProvider;},
                  {representation = RelativeFieldColorsParameters; provider = ConfigurationDataProvider;},
                  {representation = RobotCameraMatrix; provider = RobotCameraMatrixProvider;},
                  {representation = RobotDimensions; provider = ConfigurationDataProvider;},
                  {representation = ScanGrid; provider = ScanGridProvider;},
              ];
          },{
              name = Cognition;
              priority = 1;
              debugReceiverSize = 2000000;
              debugSenderSize = 2000000;
              debugSenderInfrastructureSize = 200000;
              executionUnit = Cognition;
              representationProviders = [
                  {representation = BallPercept; provider = PerceptionBallPerceptProvider;},
                  {representation = BodyContour; provider = PerceptionBodyContourProvider;},
                  {representation = CameraInfo; provider = PerceptionCameraInfoProvider;},
                  {representation = CameraMatrix; provider = PerceptionCameraMatrixProvider;},
                  {representation = CameraStatus; provider = PerceptionCameraStatusProvider;},
                  {representation = CirclePercept; provider = PerceptionCirclePerceptProvider;},
                  {representation = FieldBoundary; provider = PerceptionFieldBoundaryProvider;},
                  {representation = FieldLines; provider = PerceptionFieldLinesProvider;},
                  {representation = FieldLineIntersections; provider = PerceptionFieldLineIntersectionsProvider;},
                  {representation = FrameInfo; provider = PerceptionFrameInfoProvider;},
                  {representation = ImageCoordinateSystem; provider = PerceptionImageCoordinateSystemProvider;},
                  {representation = IntersectionsPercept; provider = PerceptionIntersectionsPerceptProvider;},
                  {representation = LinesPercept; provider = PerceptionLinesPerceptProvider;},
                  {representation = ObstaclesFieldPercept; provider = PerceptionObstaclesFieldPerceptProvider;},
                  {representation = PenaltyMarkPercept; provider = PerceptionPenaltyMarkPerceptProvider;},
                  {representation = RobotCameraMatrix; provider = PerceptionRobotCameraMatrixProvider;},

                  {representation = ActivationGraph; provider = BehaviorControl;},
                  {representation = AlternativeRobotPoseHypothesis; provider = AlternativeRobotPoseProvider;},
                  {representation = ArmMotionRequest; provider = BehaviorControl;},
                  {representation = AudioData; provider = AudioProvider;},
                  {representation = BallContactChecker; provider = BallContactCheckerProvider;},
                  {representation = BallDropInModel; provider = BallDropInLocator;},
                  {representation = BallInGoal; provider = BallInGoalTracker;},
                  {representation = BallModel; provider = BallStateEstimator;},
                  {representation = BallPlayerStrategy; provider = BallPlayerStrategyProvider;},
                  {representation = BallSpecification; provider = ConfigurationDataProvider;},
                  {representation = BehaviorStatus; provider = BehaviorControl;},
                  {representation = NaovaMessageOutputGenerator; provider = TeamMessageHandler;},
                  {representation = CameraCalibration; provider = AutomaticCameraCalibrator;},
                  {representation = CalibrationRequest; provider = BehaviorControl;},
                  {representation = CameraCalibrationStatus; provider = AutomaticCameraCalibrator;},
                  {representation = CameraResolutionRequest; provider = AutomaticCameraCalibrator;},
                  {representation = CurrentTactic; provider = TacticProvider;},
                  {representation = DamageConfigurationBody; provider = ConfigurationDataProvider;},
                  {representation = DamageConfigurationHead; provider = ConfigurationDataProvider;},
                  {representation = DynamicSupporterPositionning; provider = DynamicSupporterPositionningProvider;},
                  {representation = EnhancedKeyStates; provider = KeyStateEnhancer;},
                  {representation = ExtendedGameInfo; provider = ExtendedGameInfoProvider;},
                  {representation = FieldBall; provider = FieldBallProvider;},
                  {representation = FieldCoverage; provider = FieldCoverageProvider;},
                  {representation = FieldDimensions; provider = ConfigurationDataProvider;},
                  {representation = FieldFeatureOverview; provider = FieldFeatureOverviewProvider;},
                  {representation = FieldRating; provider = FieldRatingProvider;},
                  {representation = FieldScore; provider = FieldScoreProvider;},
                  {representation = FilteredBallPercepts; provider = BallPerceptFilter;},
                  {representation = FootSoleRotationCalibration; provider = FootSoleRotationCalibrationProvider;},
                  {representation = GameInfo; provider = WhistleHandler;},
                  {representation = GlobalFieldCoverage; provider = GlobalFieldCoverageProvider;},
                  {representation = HeadAngleRequest; provider = CameraControlEngine;},
                  {representation = HeadLimits; provider = ConfigurationDataProvider;},
                  {representation = HeadMotionRequest; provider = BehaviorControl;},
                  {representation = IMUCalibration; provider = IMUCalibrationProvider;},
                  {representation = IntersectionRelations; provider = ConfigurationDataProvider;},
                  {representation = JointLimits; provider = ConfigurationDataProvider;},
                  {representation = KickInfo; provider = ConfigurationDataProvider;},
                  {representation = KickoffState; provider = KickoffStateProvider;},
                  {representation = LEDRequest; provider = LEDHandler;},
                  {representation = LibCheck; provider = LibCheckProvider;},
                  {representation = LibLookActive; provider = LibLookActiveProvider;},
                  {representation = LibPosition; provider = LibPositionProvider;},
                  {representation = LibTeam; provider = LibTeamProvider;},
                  {representation = LibTeammates; provider = LibTeammatesProvider;},
                  {representation = LibWalk; provider = LibWalkProvider;},
                  {representation = MidCircle; provider = MidCirclePerceptor;},
                  {representation = MotionRequest; provider = BehaviorControl;},
                  {representation = ObstacleModel; provider = ObstacleModelProvider;},
                  {representation = Odometer; provider = OdometerProvider;},
                  {representation = OpponentTeamInfo; provider = GameDataProvider;},
                  {representation = OwnTeamInfo; provider = GameDataProvider;},
                  {representation = PathPlanner; provider = PathPlannerProvider;},
                  {representation = PenaltyArea; provider = PenaltyAreaPerceptor;},
                  {representation = PenaltyMarkWithPenaltyAreaLine; provider = PenaltyMarkWithPenaltyAreaLinePerceptor;},
                  {representation = PerceptRegistration; provider = PerceptRegistrationProvider;},
                  {representation = RawGameInfo; provider = GameDataProvider;},
                  {representation = RobotDimensions; provider = ConfigurationDataProvider;},
                  {representation = RobotHealth; provider = RobotHealthProvider;},
                  {representation = RobotInfo; provider = GameDataProvider;},
                  {representation = RobotPose; provider = SelfLocator;},
                  {representation = SelfLocalizationHypotheses; provider = SelfLocator;},
                  {representation = SetupPoses; provider = ConfigurationDataProvider;},
                  {representation = SideInformation; provider = SideInformationProvider;},
                  {representation = StaticInitialPose; provider = StaticInitialPoseProvider;},
                  {representation = SupporterPositioning; provider = SupporterPositioningProvider;},
                  {representation = TeamActivationGraph; provider = TeamBehaviorControl;},
                  {representation = TeamBallModel; provider = TeamBallLocator;},
                  {representation = TeamBehaviorStatus; provider = TeamBehaviorControl;},
                  {representation = TeamData; provider = TeamMessageHandler;},
                  {representation = TeamPlayersModel; provider = TeamPlayersLocator;},
                  {representation = TeamTalk; provider = BehaviorControl;},
                  {representation = Whistle; provider = WhistleRecognizer;},
                  {representation = WorldModelPrediction; provider = WorldModelPredictor;},
              ];
          },{
              name = Motion;
              priority = 20;
              debugReceiverSize = 500000;
              debugSenderSize = 130000;
              debugSenderInfrastructureSize = 100000;
              executionUnit = Motion;
              representationProviders = [
                  {representation = ArmContactModel; provider = ArmContactModelProvider;},
                  {representation = ArmKeyFrameGenerator; provider = ArmKeyFrameEngine;},
                  {representation = ArmMotionInfo; provider = MotionEngine;},
                  {representation = BallSpecification; provider = ConfigurationDataProvider;},
                  {representation = DamageConfigurationBody; provider = ConfigurationDataProvider;},
                  {representation = DamageConfigurationHead; provider = ConfigurationDataProvider;},
                  {representation = DribbleGenerator; provider = DribbleEngine;},
                  {representation = DynamicTesting; provider = DynamicController;},
                  {representation = EnergySaving; provider = EnergySavingProvider;},
                  {representation = FallDownState; provider = FallDownStateProvider;},
                  {representation = FallGenerator; provider = FallEngine;},
                  {representation = FilteredCurrent; provider = FilteredCurrentProvider;},
                  {representation = FootBumperState; provider = FootBumperStateProvider;},
                  {representation = FootSupport; provider = FootSupportProvider;},
                  {representation = FootOffset; provider = ConfigurationDataProvider;},
                  {representation = FrameInfo; provider = NaoProvider;},
                  {representation = FsrSensorData; provider = NaoProvider;},
                  {representation = GetUpGenerator; provider = KeyframeMotionEngine;},
                  {representation = GlobalOptions; provider = ConfigurationDataProvider;},
                  {representation = GroundContactState; provider = GroundContactDetector;},
                  {representation = GyroOffset; provider = GyroOffsetProvider;},
                  {representation = GyroState; provider = GyroStateProvider;},
                  {representation = HeadLimits; provider = ConfigurationDataProvider;},
                  {representation = HeadMotionGenerator; provider = HeadMotionEngine;},
                  {representation = HeadMotionInfo; provider = MotionEngine;},
                  {representation = InertialData; provider = InertialDataProvider;},
                  {representation = InertialSensorData; provider = NaoProvider;},
                  {representation = JointAngles; provider = JointAnglesProvider;},
                  {representation = JointCalibration; provider = ConfigurationDataProvider;},
                  {representation = JointLimits; provider = ConfigurationDataProvider;},
                  {representation = JointRequest; provider = MotionEngine;},
                  {representation = JointSensorData; provider = NaoProvider;},
                  {representation = KeyframeMotionGenerator; provider = KeyframeMotionEngine;},
                  {representation = KeyframeMotionParameters; provider = ConfigurationDataProvider;},
                  {representation = KeyStates; provider = NaoProvider;},
                  {representation = KickGenerator; provider = KickEngine;},
                  {representation = KickInfo; provider = ConfigurationDataProvider;},
                  {representation = MassCalibration; provider = ConfigurationDataProvider;},
                  {representation = MotionInfo; provider = MotionEngine;},
                  {representation = MotionRobotHealth; provider = MotionRobotHealthProvider;},
                  {representation = OdometryData; provider = MotionEngine;},
                  {representation = PointAtGenerator; provider = PointAtEngine;},
                  // {representation = ReplayWalkRequestGenerator; provider = ReplayWalkRequestProvider;},
                  {representation = RobotDimensions; provider = ConfigurationDataProvider;},
                  {representation = RobotModel; provider = RobotModelProvider;},
                  {representation = StandGenerator; provider = WalkingEngine;},
                  {representation = StiffnessSettings; provider = ConfigurationDataProvider;},
                  {representation = SystemSensorData; provider = NaoProvider;},
                  {representation = TorsoMatrix; provider = TorsoMatrixProvider;},
                  {representation = WalkAtAbsoluteSpeedGenerator; provider = WalkAtSpeedEngine;},
                  {representation = WalkAtRelativeSpeedGenerator; provider = WalkAtSpeedEngine;},
                  {representation = WalkGenerator; provider = WalkingEngine;},
                  {representation = WalkingEngineOutput; provider = WalkingEngine;},
                  {representation = WalkKickGenerator; provider = WalkKickEngine;},
                  {representation = WalkLearner; provider = WalkLearnerProvider;},
                  {representation = WalkModifier; provider = ConfigurationDataProvider;},
                  {representation = WalkStepData; provider = WalkingEngine;},
                  {representation = WalkToBallGenerator; provider = WalkToBallEngine;},
                  {representation = WalkToBallAndKickGenerator; provider = WalkToBallAndKickEngine;},
                  {representation = WalkToPoseGenerator; provider = WalkToPoseEngine;},
              ];
          },
      ];

Explications
------------

Nous allons ajouter notre représentation dans le fichier de configuration (*thread.cfg*) qui se trouve dans le répertoire ``Config/Scenarios/Default/``.  
Comme expliqué dans :ref:`core-concepts`, le système s'appuie sur plusieurs threads parallèles, chacun ayant une fonction spécifique.  
Par exemple, les threads de perception traitent les images des caméras, tandis que d'autres gèrent la cognition, 
le mouvement ou encore la communication avec un PC distant pour le débogage.

Ici, nous nous concentrons sur le thread « Upper » de la caméra, 
car il correspond à la caméra frontale du NAO, 
offrant ainsi une vision directement orientée vers l'avant du robot.

Il est important d'ajouter la représentation et son fournisseur dans la section correspondante, en respectant l'ordre alphabétique.

.. code-block:: cfg

   {representation = ColorDetect; provider = ColorDetector;},

Vous venez ainsi d'intégrer la représentation dans le fichier de configuration. 
Passez maintenant au tutoriel suivant pour poursuivre l'intégration de cette représentation dans l'ensemble du système.