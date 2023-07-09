# moving-with-phy
simple moving with phyton
# generate and send the correct commands to the robot
def _send_robot_commands( self ):
  # ...
  v_l, v_r = self._uni_to_diff( v, omega )
  self.robot.set_wheel_drive_rates( v_l, v_r )

def _uni_to_diff( self, v, omega ):
  # v = translational velocity (m/s)
  # omega = angular velocity (rad/s)

  R = self.robot_wheel_radius
  L = self.robot_wheel_base_length

  v_l = ( (2.0 * v) - (omega*L) ) / (2.0 * R)
  v_r = ( (2.0 * v) + (omega*L) ) / (2.0 * R)

  return v_l, v_r
